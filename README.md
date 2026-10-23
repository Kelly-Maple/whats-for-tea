# What's for Tea

Easy dinner ideas, a weekly meal plan and an automatic shopping list, with a recipe book the whole group shares.

- **Ideas:** 40 simple recipes. Filter by main (chicken, beef…), style (Mexican, Italian…), under 30 minutes, kid-friendly, one pan or slow cooker. Amounts scale to however many people you're cooking for.
- **Week:** plan Monday to Sunday, mark leftovers or eating-out nights, or let it fill the empty nights for you.
- **Shopping:** every ingredient from your week, added up and sorted by supermarket aisle. Tick things off, add extras, copy the list.
- **Add recipe:** add family favourites with a photo. They go into the shared book for everyone.

Your week and shopping list stay on your own phone. The recipe book is shared.

---

## Setting it up (about 15 minutes, all free)

### 1. Make the shared recipe book (Firebase)

1. Go to https://console.firebase.google.com and sign in with a Google account.
2. Click **Create a project**, name it `whats-for-tea`, and switch Google Analytics **off**.
3. In the left menu open **Build → Authentication → Get started**. Under **Sign-in method** choose **Anonymous**, switch it on and **Save**.
   (Nobody needs a login. This just lets the app give each phone an ID so people can only delete their own recipes.)
4. Open **Build → Firestore Database → Create database**. Pick the location **australia-southeast1 (Sydney)** and **Start in production mode**.
5. In Firestore, open the **Rules** tab, delete what's there, paste in everything from `firestore.rules`, and click **Publish**.
6. Click the gear icon → **Project settings**. Under **Your apps** click the web icon `</>`, call it `What's for Tea` (leave Firebase Hosting unticked) and click **Register app**.
7. You'll see a block of code with `firebaseConfig`. Copy each value (`apiKey`, `authDomain`, `projectId`, `storageBucket`, `messagingSenderId`, `appId`) into the matching line of `firebase-config.js` and save it.

These values are fine to publish. The rules from step 5 decide what people can do.

### 2. Put it on the internet (GitHub Pages)

1. Go to https://github.com/new. Name the repository `whats-for-tea`, set it to **Public**, and click **Create repository**.
2. On the next page click **uploading an existing file**. Drag in **all the files** from this folder, then click **Commit changes**.
3. Open the repository's **Settings → Pages**. Under **Build and deployment** set Source to **Deploy from a branch**, choose **main** and **/ (root)**, then **Save**.
4. After a minute or two the site is live at `https://YOUR-GITHUB-NAME.github.io/whats-for-tea/`. Send that link to your friends.

To change something later (like the Firebase settings), open the file on GitHub, click the pencil to edit, and commit. The site updates within a couple of minutes.

### 3. Put it on your phone like an app

- **iPhone:** open the link in Safari → tap Share → **Add to Home Screen**.
- **Android:** open the link in Chrome → tap ⋮ → **Install app** (or **Add to Home screen**).

---

## Good to know

- Anyone with the link can see and add recipes, so share it with people you're happy to cook with.
- Firebase's free plan is far more than a group of friends will ever use.
- If the shared book isn't connected, the app shows a note and still works, but new recipes only save on that phone.
