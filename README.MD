## Java Unix Timestamp 변환 

#### Unix timestamp를 Date String으로 변환하는 함수

```
private static String getTimestampToDate(String timestampStr){
       long timestamp = Long.parseLong(timestampStr);
       Date date = new java.util.Date(timestamp*1000L); 
       SimpleDateFormat sdf = new java.text.SimpleDateFormat("yyyy-MM-dd HH:mm:ss"); 
       sdf.setTimeZone(java.util.TimeZone.getTimeZone("GMT+9")); 
       String formattedDate = sdf.format(date);
       return formattedDate;
   }
```

```
public static void main(String[] args) throws IOException{
       String dateStr = getTimestampToDate("1563336439");
       System.out.println(dateStr);
   }
```
## Java 6 and Java 7

- encofing
```
byte[] message = "hello world".getBytes("UTF-8");
String encoded = DatatypeConverter.printBase64Binary(message);
System.out.println(encoded);
```
- decoding
```$xslt
byte[] decoded = DatatypeConverter.parseBase64Binary("aGVsbG8gd29ybGQ=");
System.out.println(new String(decoded, "UTF-8"));
```

## Java 8 version (java.util.Base64 encoding 사용)   

### Text -> hex
```
  byte[] message = "hello world".getBytes(StandardCharsets.UTF_8);
     String encoded = Base64.getEncoder().encodeToString(message);
     System.out.println(encoded);
```

### hex -> Text(decoding)
```
byte[] decoded = Base64.getDecoder().decode("aGVsbG8gd29ybGQ=");
System.out.println(new String(decoded, StandardCharsets.UTF_8));
```
 