# kobo-tweaks
//TODO install a combination of the below things on my Kobo e-reader

launcher: https://github.com/niluje/kfmon

document reader: https://github.com/baskerville/plato

script launcher: https://github.com/geek1011/NickelMenu/

## sqlite scripts

first get sqlite file from  `KOBOeReader > .kobo > KoboReader.sqlite`

**list highlights and annotations by ISBN and book:**
```
select 
ISBN, title,
text, annotation
from bookmark
left outer join content
on (content.contentID=bookmark.VolumeID and content.ContentType=6)
where  
text is not null;
```

**Book details:**
```
SELECT 
ContentID as BOOKID,
ISBN, title,subtitle, attribution, Language,  Description
FROM content WHERE contenttype=6 AND Accessibility=1 
order by DateLastRead DESC;
```

