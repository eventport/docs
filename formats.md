## Event Format

See example_event.json for an example.

#### _id (String)

Our event id.

#### name (String)

The title of the event.

#### subtitle (String)

The subtitle of the event.

#### organizer (String)

The organizer of the event.

#### remark (String)

Notes for publishers regarding the event. For example background information regarding changes, sale starts etc.

#### multiDay (boolean)

When this flag is set to true, the event will last more than one day (see begin and end).
When the flag  is set to false, the event is shorter than 24 hours.

#### begin (Date and Time)

Begin date and time in ISO-8601 format and UTC timezone.

#### end (Date and Time)

End date and time in ISO-8601 format and UTC timezone.

#### openEnd (Boolean)

If set to true then the event has no end time (ignore the end time).

#### description (String)

The description of the event. There are also additional descriptions for each channel under the channel property.

#### genres (Array of Strings)

A list of music genres of the event.

#### types (Array of Strings)

A list of event types.

#### location (Object)

##### location._id (String)

The location id.

##### location.name (String)

The location name.

##### location.street (String)

The location street with house number.

##### location.addressAddition (String)

The location addressAddition.

##### location.postalcode (String)

The location postalcode.

##### location.city (String)

The location city.

##### location.homepage (String)

The location homepage URL.

##### location.facebookPageId (String)

The Facebook page ID of the location.

####  floors (Array of Strings)

The floors of the location where the event takes place.

#### lineup (Array of Lineup Objects)

The event lineup.

#### artists (Array of Artist Objects)

#### preSalePrice (Float)

The pre-sale ticket price in euros.

#### boxOfficePrice (Float)

The box office ticket price in euros.

#### specialPrice (Float)

A special price that can be connected with a condition.

#### specialPriceConditions (String)

The conditions for the special price.

#### photos (Array of Photo Objects)

Photos can have the format JPEG, PNG or GIF.

#### documents (Array of Document Objects)

#### tickets (Array of Ticket Objects)

URLs to ticket services where you can buy tickets for the event.

#### media (Array of String)

Links to Soundcloud, YouTube, Vimeo etc.

#### channels (Object)

##### channels.facebook (Object)

Facebook specific event info.

###### channels.facebook.id (String)

The id of the Facebook event.

###### channels.facebook.url (String)

The url of the Facebook event.

###### channels.facebook.description (String)

The description of the event that is used for Facebook.

###### channels.facebook.useGeneralDescription (Boolean)

True if the general event description is used for Facebook.
When false, `channels.facebook.description` can have another value than `description`.

###### channels.facebook.postTimeType (Number) (internal)

- 0: Manually posted
- 1: Automatically posted at fixed time
- 2: Automatically posted at time that is relative to the event begin

###### channels.facebook.postTime (Date) (internal)

The date and time when the event should be posted automatically when postTimeType is not 0.

##### channels.homepage (Object)

User homepage specific event info.

###### channels.homepage.description (String)

The description of the event that should be used for the homepage of the user.

###### channels.homepage.useGeneralDescription (Boolean)

True if the general event description is used for the homepage.
When false, `channels.homepage.description` can have another value than `description`.

###### channels.homepage.customFields (Object)

The map of custom field names and their values.
Custom fields can be added in the settings.
They will appear as additional fields in the event form.

##### channels.publisherNewsletter (Object) (internal)

TODO: Document

##### channels.userNewsletter (Object) (internal)

TODO: Document

#### rescheduled (Boolean)

True if the event was rescheduled.

#### relocated (Boolean)

True if the event was relocated.

#### cancelled

True if the event was cancelled.


## Photo Format

#### _id (String)

The id of the photo.

#### url (String)

The url of the photo with the original resolution. The maximum file size is currently 5MB.

#### thumbnailUrl

The url of the photo as thumbnail (100x100).

#### purposes (Array of Strings)

See below.

#### title (String)

The title of the photo.

## Document Format

#### _id (String)

The id of the document.

#### url (String)

The url of the document. The maximum file size is currently 5MB.

#### thumbnailUrl

The url of the photo as thumbnail (100x100).

#### purposes (Array of Strings)

See below.

#### title (String)

The title of the photo.


## Lineup Format

#### artists (Array of Artist Objects)

#### floors (Array of Strings)

The names of the floors.

#### from (Object)

##### from.date (Date)

From date of the lineup in ISO-8601 format and UTC timezone.

##### from.time (Time)

From time of the lineup in ISO-8601 format and UTC timezone.

#### to (Object)

##### to.date (Date)

To date of the lineup in ISO-8601 format and UTC timezone.

##### to.time (Time)

To time of the lineup in ISO-8601 format and UTC timezone.

#### genres (Array of Strings)

List of the genres the artist plays.


## Artist Format

#### _id (String)

The id of the artist.

#### name (String)

The name of the artist.


## Photo and Document Purposes

We have some special purposes that currently use numbers instead of names. The user can also use own purposes that will be saved as text.

#### Special photo purposes

```
eventPhotoPurposes = {
  'PUBLISHER': '0',             // Make the photo available for publishers
  'HOMEPAGE': '1',              // The photo should be used on the homepage
  'FACEBOOK': '2',              // The photo is used as Facebook cover photo
  'FLYER_FRONT': '3',           // The front side of the event flyer
  'FLYER_BACK': '4',            // The back side of the event flyer
  'PUBLISHER_NEWSLETTER': '5',  // The photo is used in the publisher newsletter
  'HOMEPAGE_MAIN_PHOTO': '6'    // The main photo for the homepage. Only one photo has this purpose.
};
```

#### Special document purposes
```
eventDocumentPurposes = {
  'PUBLISHER': '0',           // Make the document available for publishers
  'HOMEPAGE': '1'             // The document should be used on the homepage
};
```
