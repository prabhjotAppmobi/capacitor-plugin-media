# @whiteguru/capacitor-plugin-media

Capacitor plugin to handle media files

## Install

```bash
npm install @whiteguru/capacitor-plugin-media
npx cap sync
```

## API

<docgen-index>

* [`getMedias(...)`](#getmedias)
* [`getAlbums()`](#getalbums)
* [`savePhoto(...)`](#savephoto)
* [`saveVideo(...)`](#savevideo)
* [`saveGif(...)`](#savegif)
* [`saveDocument(...)`](#savedocument)
* [`createAlbum(...)`](#createalbum)
* [Interfaces](#interfaces)
* [Enums](#enums)

</docgen-index>

<docgen-api>
<!--Update the source file JSDoc comments and rerun docgen to update the docs below-->

### getMedias(...)

```typescript
getMedias(options?: MediaFetchOptions | undefined) => Promise<MediaResponse>
```

Get list of user medias. Only for IOS

| Param         | Type                                                            |
| ------------- | --------------------------------------------------------------- |
| **`options`** | <code><a href="#mediafetchoptions">MediaFetchOptions</a></code> |

**Returns:** <code>Promise&lt;<a href="#mediaresponse">MediaResponse</a>&gt;</code>

--------------------


### getAlbums()

```typescript
getAlbums() => Promise<MediaAlbumResponse>
```

Get list of user albums

**Returns:** <code>Promise&lt;<a href="#mediaalbumresponse">MediaAlbumResponse</a>&gt;</code>

--------------------


### savePhoto(...)

```typescript
savePhoto(options?: MediaSaveOptions | undefined) => Promise<PhotoResponse>
```

Add image to gallery. Create album if not exists.

| Param         | Type                                                          |
| ------------- | ------------------------------------------------------------- |
| **`options`** | <code><a href="#mediasaveoptions">MediaSaveOptions</a></code> |

**Returns:** <code>Promise&lt;<a href="#photoresponse">PhotoResponse</a>&gt;</code>

--------------------


### saveVideo(...)

```typescript
saveVideo(options?: MediaSaveOptions | undefined) => Promise<PhotoResponse>
```

Add video to gallery. Create album if not exists.

| Param         | Type                                                          |
| ------------- | ------------------------------------------------------------- |
| **`options`** | <code><a href="#mediasaveoptions">MediaSaveOptions</a></code> |

**Returns:** <code>Promise&lt;<a href="#photoresponse">PhotoResponse</a>&gt;</code>

--------------------


### saveGif(...)

```typescript
saveGif(options?: MediaSaveOptions | undefined) => Promise<PhotoResponse>
```

Add gif to gallery. Create album if not exists.

| Param         | Type                                                          |
| ------------- | ------------------------------------------------------------- |
| **`options`** | <code><a href="#mediasaveoptions">MediaSaveOptions</a></code> |

**Returns:** <code>Promise&lt;<a href="#photoresponse">PhotoResponse</a>&gt;</code>

--------------------


### saveDocument(...)

```typescript
saveDocument(options?: MediaSaveOptions | undefined) => Promise<PhotoResponse>
```

Add document to gallery. Only for Android. Create album if not exists.

| Param         | Type                                                          |
| ------------- | ------------------------------------------------------------- |
| **`options`** | <code><a href="#mediasaveoptions">MediaSaveOptions</a></code> |

**Returns:** <code>Promise&lt;<a href="#photoresponse">PhotoResponse</a>&gt;</code>

--------------------


### createAlbum(...)

```typescript
createAlbum(options: MediaAlbumCreate) => Promise<MediaAlbum>
```

Create album

| Param         | Type                                                          |
| ------------- | ------------------------------------------------------------- |
| **`options`** | <code><a href="#mediaalbumcreate">MediaAlbumCreate</a></code> |

**Returns:** <code>Promise&lt;<a href="#mediaalbum">MediaAlbum</a>&gt;</code>

--------------------


### Interfaces


#### MediaResponse

| Prop         | Type                      |
| ------------ | ------------------------- |
| **`medias`** | <code>MediaAsset[]</code> |


#### MediaAsset

| Prop                  | Type                                                    | Description                                                             |
| --------------------- | ------------------------------------------------------- | ----------------------------------------------------------------------- |
| **`identifier`**      | <code>string</code>                                     | Platform-specific identifier                                            |
| **`data`**            | <code>string</code>                                     | Data for a photo asset as a base64 encoded string (JPEG only supported) |
| **`creationDate`**    | <code>string</code>                                     | ISO date string for creation date of asset                              |
| **`fullWidth`**       | <code>number</code>                                     | Full width of original asset                                            |
| **`fullHeight`**      | <code>number</code>                                     | Full height of original asset                                           |
| **`thumbnailWidth`**  | <code>number</code>                                     | Width of thumbnail preview                                              |
| **`thumbnailHeight`** | <code>number</code>                                     | Height of thumbnail preview                                             |
| **`location`**        | <code><a href="#medialocation">MediaLocation</a></code> | Location metadata for the asset                                         |


#### MediaLocation

| Prop            | Type                | Description                              |
| --------------- | ------------------- | ---------------------------------------- |
| **`latitude`**  | <code>number</code> | GPS latitude image was taken at          |
| **`longitude`** | <code>number</code> | GPS longitude image was taken at         |
| **`heading`**   | <code>number</code> | Heading of user at time image was taken  |
| **`altitude`**  | <code>number</code> | Altitude of user at time image was taken |
| **`speed`**     | <code>number</code> | Speed of user at time image was taken    |


#### MediaFetchOptions

| Prop                   | Type                | Description                                                           |
| ---------------------- | ------------------- | --------------------------------------------------------------------- |
| **`quantity`**         | <code>number</code> | The number of photos to fetch, sorted by last created date descending |
| **`thumbnailWidth`**   | <code>number</code> | The width of thumbnail to return                                      |
| **`thumbnailHeight`**  | <code>number</code> | The height of thumbnail to return                                     |
| **`thumbnailQuality`** | <code>number</code> | The quality of thumbnail to return as JPEG (0-100)                    |
| **`types`**            | <code>string</code> | Which types of assets to return (currently only supports "photos")    |
| **`albumIdentifier`**  | <code>string</code> | Which album identifier to query in (get identifier with getAlbums())  |


#### MediaAlbumResponse

| Prop         | Type                      | Description                                   |
| ------------ | ------------------------- | --------------------------------------------- |
| **`albums`** | <code>MediaAlbum[]</code> | Array of <a href="#mediaalbum">MediaAlbum</a> |


#### MediaAlbum

| Prop             | Type                                                      | Description                        |
| ---------------- | --------------------------------------------------------- | ---------------------------------- |
| **`identifier`** | <code>string</code>                                       | Platform-specific album identifier |
| **`name`**       | <code>string</code>                                       | Album name                         |
| **`type`**       | <code><a href="#mediaalbumtype">MediaAlbumType</a></code> | Album type                         |


#### PhotoResponse

| Prop           | Type                | Description |
| -------------- | ------------------- | ----------- |
| **`filePath`** | <code>string</code> | Media path  |


#### MediaSaveOptions

| Prop        | Type                                         | Description                                                                            |
| ----------- | -------------------------------------------- | -------------------------------------------------------------------------------------- |
| **`path`**  | <code>string</code>                          | Path of file to add                                                                    |
| **`album`** | <code>{ id?: string; name?: string; }</code> | Album to add media. If no 'id' and 'name' not exists, album with name will be created. |


#### MediaAlbumCreate

| Prop       | Type                | Description |
| ---------- | ------------------- | ----------- |
| **`name`** | <code>string</code> | Album name  |


### Enums


#### MediaAlbumType

| Members      | Value                 | Description                                                    |
| ------------ | --------------------- | -------------------------------------------------------------- |
| **`Smart`**  | <code>'smart'</code>  | Album is a "smart" album (such as Favorites or Recently Added) |
| **`Shared`** | <code>'shared'</code> | Album is a cloud-shared album                                  |
| **`User`**   | <code>'user'</code>   | Album is a user-created album                                  |

</docgen-api>
