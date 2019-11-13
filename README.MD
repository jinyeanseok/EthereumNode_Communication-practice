## Java Unix Timestamp 변환 

Unix timestamp를 Date String으로 변환하는 함수

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

## Text -> hex(java8은 java.util.Base64 encoding 사용)   
```
  byte[] message = "hello world".getBytes(StandardCharsets.UTF_8);
     String encoded = Base64.getEncoder().encodeToString(message);
     System.out.println(encoded);
```
 