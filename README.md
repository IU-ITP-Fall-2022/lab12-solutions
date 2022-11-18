# Lab 12 Solutions

## Exercise 1

Write a program that reads the data from a text file and writes it into another text file. Handle the following exceptions:

* input file does not exist
* no write-permission for the output file

## Exercise 2

Write a program that reads an input from the file, which accepts two integer parameters, and divides the first integer by the second.

You have to catch all the possible exceptions (such as parsing errors, non-integer errors, and arithmetic errors) and print the appropriate message.

## Exercise 3

Update the code from a previous task to throw suppressed exceptions after printing the error messages

## Exercise 4

The method below downloads an image (actually any file). Your task is to edit the code so that it could handle all the possible exceptions.

```java
public class ImageSaver {
    public static void saveImage(String imageUrl) {
        URL url = new URL(imageUrl);
        String fileName = url.getFile();
        String destName = "./figures" + fileName.substring(fileName.lastIndexOf("/"));
        System.out.println(destName);

        InputStream is = url.openStream();
        OutputStream os = new FileOutputStream(destName);

        byte[] b = new byte[2048];
        int length;

        while ((length = is.read(b)) != -1) {
            os.write(b, 0, length);
        }

        is.close();
        os.close();
    }
}
```