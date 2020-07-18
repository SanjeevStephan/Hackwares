# Steganography
<b>Steganography</b> is a process of hiding a file, an image, a video, a text inside another file. <br/>
Steganography is a vast topic. This tutorial only covers <b>how to hide files inside images,</b> which is the core concept of Steganography. <br/>

## Hide files inside images in Linux
We can hide files inside images in different methods. Here I have given 5 methods. <br/>
* Method 1 <br/>
  This method doesn’t require any additional software. Just a basic Linux command line knowledge is enough.<br/>
  I have one image file called <b>image.jpg</b> and a directory called <b>sk</b>. <br/>
  Inside this directory, there is a file called <b>secret.txt</b> which has some confidential message. <br/>
  This is the file that we are going to embed in the <b>image.jpg</b> file. You can place any number of files you want to hide inside this directory. <br/>
  Then, I am going to compress the directory <b>sk</b> and save it as <b>secret.zip</b> to make it as single file. <br/>
  Finally, I will concatenate the zip file (<b>secret.zip</b>) and image file (<b>image.jpg</b>) using cat command and save it as <b>HiddenFileInsideImage.jpg.</b>
  
  To put things more clearly
  
  * image.jpg – A random image file.
  * sk – The directory that contains all secret files.
  * secret.zip – Archive of sk directory.
  * ostechnix.jpg – The output image file that contains both secret.zip and image.jpg.
      
* Step 1 : Put the image file and the directory in a folder. I have put them both in Documents folder.
* Step 2: Move all files you want to hide inside the folder “sk”. 
              Then, compress this folder and save it as “secret.zip”. 
              To compress the folder, just right click on it, and select compress. <br/>
  ![document folder image](https://www.ostechnix.com/wp-content/uploads/2019/08/Compress-secret-files-1.png)
* Step 3: Next open the Terminal. Go to the location where you have stored the zip and image files (In our case it is Documents). <br/>
              Finally, concatenate the secret.zip and test.jpg files, and save them as ostechnix.jpg using cat command. <br/>
              
              root@kali-linux:~$ cd Documents
              root@kali-linux:~$ cat image.jpg secret.zip > ostechnix.jpg
         <br/>
   ![command line image](https://www.ostechnix.com/wp-content/uploads/2016/08/Concatenate-files.png)
   
     That’s it. We have now hidden the confidential files inside ostechnix.jpg. It is the important file.  <br/>
     Just delete all other files except ostechnix.jpg. <br/>
     The ostechnix.jpg will look like an ordinary image file and anyone can view it using any image viewer application. <br/>
     But, they might not know this file has some confidential file in it. <br/>
     To view the hidden files inside the image file ostechnix.jpg, just uncompress it using the following command: <br/>
       
     The ostechnix.jpg will look like an ordinary image file and anyone can view it using any image viewer application. <br/> 
     But, they might not know this file has confidential file in it. <br/> 

     To view the hidden files inside the image file ostechnix.jpg, just uncompress it using the following command: <br/> 
                
      $ unzip ostechnix.jpg
       |Or|
      $ unzip -t ostechnix.jpg
      
     ![extract files](https://www.ostechnix.com/wp-content/uploads/2016/08/Unzip-image-file.png)
     
     Or Simply Rename the File from <b>some_image_file.jpg</b> to <b>anyfiles.zip</b>.
     
     As you see in the above output, the directory sk that has secret files inside has been extracted. Now, go back to the folder and check the contents. 
     You will see all the files in there.
      
   ## For More Information | Go to <a href="https://www.ostechnix.com/">ostechnix.com</a>
   https://www.ostechnix.com/hide-files-inside-images-linux/
