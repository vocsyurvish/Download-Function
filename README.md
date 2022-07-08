# Download-Function


<Details>
<Summary>Drawable Download to Storage.</Summary>

```java
  try {
    Bitmap bm = BitmapFactory.decodeResource(getResources(), R.drawable.ic_launcher_round);
    String extStorageDirectory = getApplicationContext().getCacheDir().toString();
    File file = new File(extStorageDirectory, "ic_launcher.png");
    FileOutputStream outStream = new FileOutputStream(file);
    bm.compress(Bitmap.CompressFormat.PNG, 100, outStream);
    outStream.flush();
    outStream.close();
  } catch (Exception e) {
    Log.e("TAG", "onCreate: " + e.getMessage());
  }
```

</Details>

  
<Details>
<Summary>Raw files Download to Storage.</Summary>
  
- rawId = R.raw.your_raw_file_name;
- destinationFile = where you store the raw file...
  
```java
            InputStream in = null;
            FileOutputStream fout = null;
            try {
                in = activity.getResources().openRawResource(rawId);
                fout = new FileOutputStream(destinationFile);

                final byte data[] = new byte[1024];
                int count;
                while ((count = in.read(data, 0, 1024)) != -1) {
                    fout.write(data, 0, count);
                }
                if (in != null) {
                    in.close();
                }
                if (fout != null) {
                    fout.close();
                }
            } catch (Exception e) {
                e.printStackTrace();
            }
```
  
<Details>
