# APIs

An API is an interface. It's something that has been created to help two different systems interact with one another.

#### Benefits

1. It doesn't expose the implementation to those who shouldn't have access to it
2. The API provides a standard way of accessing the application
3. It makes it much easier to understand how to access the application's data

Frequently used APIs are

- [Google Maps API](https://developers.google.com/maps/documentation/) allows users to access a large amount of data related to maps, routes, and places around the world.
- [Stripe API](https://stripe.com/docs/api?utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier&utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier) allows users to accept payments, send payouts, and manage businesses online.

* [Facebook API](https://developers.facebook.com/docs) allows developers to integrate directly with the Facebook platform.

- [Instagram Basic Display API](https://developers.facebook.com/docs/instagram-basic-display-api) allows users of your app to get basic profile information, photos, and videos in their Instagram accounts.
- [Spotify API](https://developer.spotify.com/documentation/web-api/) allows users to access a large amount of data related to music artists, albums, and tracks, directly from the Spotify Data Catalogue.

#### Client-Server Communication

1. Client sends a request to the API server
2. The API server parses that request
3. Assuming the request is formatted correctly, the server queries the database for the information or performs the action in the request
4. The server formats the response and sends it back to the client
5. The client renders the response according to its implementation
