<template>
  <div>Data returned from firestore is: {{ this.firestoreData }}</div>
</template>
<script lang="ts">
import { Options, Vue } from "vue-class-component";
import {
  initializeFirestore,
  CACHE_SIZE_UNLIMITED,
  enableIndexedDbPersistence,
  query,
  collection,
  onSnapshot,
  Firestore,
  DocumentData,
} from "firebase/firestore";
import { FirebaseApp, initializeApp } from "firebase/app";

@Options({})
export default class App extends Vue {
  db: Firestore | null = null;
  firestoreData: DocumentData[] | null = null;

  /** This initalizes the firestore database with persistence enabled */
  initFirestore(): Promise<void> {
    /** NOTE: This entire function runs without any errors! */

    this.db = initializeFirestore(this.firebaseApp, {
      cacheSizeBytes: CACHE_SIZE_UNLIMITED,
    });
    return enableIndexedDbPersistence(this.db);
  }

  /** This attempts to fetch data from a colleciton ["test_collection"] in firebase */
  getData(): void {
    /** Listening to data (or getting data) when persistence is enabled causes the error (see browser console logs) */
    if (this.db == null) return;
    const q = query(collection(this.db, "test_collection"));
    onSnapshot(q, (snap) => {
      this.firestoreData = snap.docs.map((doc) => doc.data());
    });
  }

  /** Basic firebase app initialization */
  get firebaseApp(): FirebaseApp {
    const firebaseConfig = {
      apiKey: "AIzaSyB3_wPLR6kxsaogh-Lzby_VrhfEDxwTE44",
      authDomain: "fir-db-persistence-error.firebaseapp.com",
      projectId: "fir-db-persistence-error",
      storageBucket: "fir-db-persistence-error.appspot.com",
      messagingSenderId: "335398653330",
      appId: "1:335398653330:web:ac66ec82e6ff19d548c54b",
    };
    return initializeApp(firebaseConfig);
  }

  mounted(): void {
    this.initFirestore().then(() => this.getData());
  }
}
</script>
