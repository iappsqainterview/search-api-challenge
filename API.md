iTunes Search API
=============

Overview
-------------

The Search API allows you to place search fields in your website to search for content within the iTunes Store, App Store, iBooks Store and Mac App Store. You can search for a variety of content; including apps, iBooks, movies, podcasts, music, music videos, audiobooks, and TV shows.



Searching
-------------

A fully-qualified URL to search must have the following format:

`https://itunes.apple.com/search?[parameterkeyvalue]`

Where [parameterkeyvalue] can be one or more parameter key and value pairs indicating the details of your query.

To construct a parameter key and value pair, you must concatenate each parameter key with an equal sign (=) and a value string. For example: `key1=value1` 

To create a string of parameter key and value pairs, you must concatenate each pair using an ampersand (&). For example: `key1=value1&key2=value2&key3=value3`



Parameters
-------------

The following table defines the parameter keys and values you can specify to search for content within the iTunes Store, App Store, iBooks Store and Mac App Store:


<table>
    <tr>
      <th>Parameter Key</th>
      <th>Description</th> 
      <th>Required</th>
      <th>Values</th>
    </tr>
    <tr>
        <td>term</td>
        <td>The URL-encoded text string you want to search for.<br><br>
            For example : 'jack+johnson'</td>
        <td>Y</td>
        <td>Any URL-encoded text string.

Note: URL encoding replaces spaces with the plus (+) character and all characters except the following are encoded: letters, numbers, periods (.), dashes (-), underscores (_), and asterisks (*).</td>
    </tr>
    <tr>
        <td>country</td>
        <td>The two-letter country code for the store you want to search. The search uses the default store front for the specified country. <br><br>
        For example : 'US'<br>
        The default is 'US'</td>
        <td>N</td>
        <td>See http://en.wikipedia.org/wiki/ISO_3166-1_alpha-2 for a list of ISO Country Codes.</td>
    </tr>
    <tr>
        <td>media</td>
        <td>The media type you want to search for.<br><br> 
            For example : 'movie'<br>
            The default is 'all'</td>
        <td>N</td>
        <td>movie, podcast, music, musicVideo, audiobook, shortFilm, tvShow, software, ebook, all</td>
    </tr>
    <tr>
        <td>limit</td>
        <td>The number of search results you want the iTunes Store to return.<br><br> 
            For example : 25<br>
            The default is 50</td>
        <td>N</td>
        <td>1 to 200</td>
    </tr>
</table>

Example Response
-------------

Here is an example of a response for a request with the parameter `media=music` :

```json
{
  "resultCount": 1,
  "results": [
    {
      "wrapperType": "track",
      "kind": "song",
      "artistId": 909253,
      "collectionId": 879273552,
      "trackId": 879273565,
      "artistName": "Jack Johnson",
      "collectionName": "In Between Dreams",
      "trackName": "Better Together",
      "collectionCensoredName": "In Between Dreams",
      "trackCensoredName": "Better Together",
      "artistViewUrl": "https://itunes.apple.com/us/artist/jack-johnson/id909253?uo=4",
      "collectionViewUrl": "https://itunes.apple.com/us/album/better-together/id879273552?i=879273565&uo=4",
      "trackViewUrl": "https://itunes.apple.com/us/album/better-together/id879273552?i=879273565&uo=4",
      "previewUrl": "https://audio-ssl.itunes.apple.com/apple-assets-us-std-000001/Music6/v4/13/22/67/1322678b-e40d-fb4d-8d9b-3268fe03b000/mzaf_8818596367816221008.plus.aac.p.m4a?accessKey=1515271290_3098706625171343788_%2Bkoi6hAC37HC1sYDu3mryzDtYS%2FaDwJaUs3dg%2FUWlH76OnJD7iNh53ouY9KEhGzYdywBuEa3riFMpcaGXYIUkguHBrKskWfSL1o4N4ime9yb0FbBiYKPRE7iXuL7bxPk6mX5YCInyNvTza0uM9okpucXb25HnNviByS5IKHWR3fHiNj3gPtQZ6hO%2Bcl2T3fgne24QsONu%2FwbOjoZUFg7pQ%3D%3D",
      "collectionPrice": 6.99,
      "trackPrice": 1.29,
      "releaseDate": "2005-03-01T08:00:00Z",
      "collectionExplicitness": "notExplicit",
      "trackExplicitness": "notExplicit",
      "discCount": 1,
      "discNumber": 1,
      "trackCount": 15,
      "trackNumber": 1,
      "country": "USA",
      "currency": "USD",
      "primaryGenreName": "Rock",
      "isStreamable": true
    }
  ]
}
```

All fields shown are expected for all responses of this type, however there may be additional fields in a response.
