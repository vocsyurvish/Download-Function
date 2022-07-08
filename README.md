# Download-Function


<Details>
<Summary>Drawable Download to Storage.</Summary>

#### - Code...

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

<Details>
