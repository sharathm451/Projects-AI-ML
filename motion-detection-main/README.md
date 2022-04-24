# motion-detection
motion-detection here exactly means capturing the only motion of the objects in the video from static position.

 - importing the required packages firstly 
 - creating the specific directory to capture frames of motion as required jpg,png or any other formats
 - creating the dataframe to record the time of movements if required.
 
 ## process:
 The usual thing after loading the required video file in opencv is converting to the grey scale format for any color or non-color multimedia files.
  - initial static frame is setted to none
  - convert the gray scale to gaussian blur so that if static frame is none then the first static frame will transform to the first gray scale frame.
  - Motion detection is possible when there is difference in static frame and motion frames, so we can create absolute difference between static frame to
      gray frames of video
  - This absolute difference frames play like besides blured video and can analyse start and end of motion of the video in dark frames.
  - The intensity of absolute difference frames values setted to 30 where the threshold value changes to high white scale intensity
      when the threshold value is greater than 30.
  - After some opencv image transformations like dilation and finding contours and including the boundary box to the objects when the  motion detection is found
 - create empty time and motion list to append the captured  motions and time of movements.
 
 Aftermath second block of code execution, it runs the four opencv video files to analyse the image processing like Grey video, absDiff video, white scale video and 
 original colour video with motion detection.
 
 ## converting frames to video:
  - After capturing the only motion of the objects in the complete video in a specific directory, list the files in the directory
  - create the required resolution video like 1280,720 as width and height as resizing of every image. 
  - set some parameters like the frames per second (fps) as required and size to the videowriter and release out.
  
## Drawbacks:
 Motion detection of the video's depend on it's lightening of the background and 
 Glitches are found mostly due to inappropriate opencv motion detection as boundary boxes on the objects

## Requirement packages
  - opencv 
  - numpy 
  - pandas
  - and it's some other dependencies packages.
 
