VORSA CITY — Firebase pre-registration setup

Files:
- vorsa city.html: website with Firebase Firestore pre-registration.
- firestore.rules: security rules for the preorders collection.

Firebase project used:
- Project ID: vorsa-store

IMPORTANT SETUP:
1. Open Firebase Console > Firestore Database > Rules.
2. Replace the rules editor content with the contents of firestore.rules.
3. Click Publish.
4. Open the website using a web host (for example GitHub Pages). Do not test by opening the HTML as file://.
5. Submit a test registration, then check Firestore > Data > preorders.

Security behavior:
- Public visitors can CREATE valid preorder documents only.
- Public visitors cannot READ, UPDATE, or DELETE preorder documents.
- View registrations from the Firebase Console while signed into the project owner account.

Limitations:
- The client creates a random Firestore document ID and shows a short reference code.
- These rules do not enforce one registration per email and do not provide strong bot/rate-limit protection.
- For guaranteed unique email registration, CAPTCHA/rate limiting, and a private admin dashboard, add a trusted Cloud Function/backend and admin authentication. Do not make the collection publicly readable.
- Firebase web config values are identifiers for a web app, not admin credentials. Never put service-account private keys in this HTML.
