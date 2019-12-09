
Steps to getting the Google Cloud Speech-to-Text working (12/9/19)
* Forked repository and then cloned it into a new folder> Transcription_Work
* Copied over the api-key from the previous repo, after checking that it appeared to still be valid.
* Copied over the sound files and placed them in the source folder.
* Ran the Homebrew installation of ffmpeg while in the Transcription_Work folder (not sure this makes any difference whatsoever...)


```python
brew install ffmpeg
```

(Homebrew updated, downloading portable-ruby-2.6.3.mavericks.bottle.tar.gz...pouring took forever.)

* Added a folder called Parts in the repo (since this is missing from the repo and the instructions).

Ran a test using the provided files
* ffmpeg split the genevieve.wav file into three parts correctly.


```python
ffmpeg -i source/genevieve.wav -f segment -segment_time 30 -c copy parts/out%09d.wav
```

* attempted to install required Python modules


```python
pip3 install -r requirements.txt
```

* failed for lack of permissions, suggested upgrading pip
* attempted to upgrade pip, doesn't appear to have worked since I'm still getting the upgrade message even though the log says that pip was upgraded...IDK.
* re-attempted to install required Python modules using sudo


```python
sudo pip3 install -r requirements.txt
```

* ran the provided python script


```python
python3 fast.py
```

* test of provided sound file was successful

Running a file that has worked previously
* cleared out the parts folder and deleted the transcript.txt file created in the test
* ran ffmpeg on makers.wav successfully, 119 clips 
* errored out, log follows


```python
(base) Jessicas-MacBook-Pro-7:speech-to-text jessibreen$ python3 fast.py
parts/.DS_Store started
parts/out000000003.wav started
parts/out000000011.wav started
parts/out000000019.wav started
parts/out000000027.wav started
parts/out000000015.wav started
parts/out000000023.wav started
parts/out000000007.wav started
parts/out000000031.wav started
parts/out000000003.wav done
parts/out000000004.wav started
parts/out000000023.wav done
parts/out000000024.wav started
parts/out000000019.wav done
parts/out000000020.wav started
parts/out000000027.wav done
parts/out000000028.wav started
parts/out000000011.wav done
parts/out000000012.wav started
parts/out000000031.wav done
parts/out000000032.wav started
parts/out000000007.wav done
parts/out000000008.wav started
parts/out000000015.wav done
parts/out000000016.wav started
parts/out000000004.wav done
parts/out000000005.wav started
parts/out000000024.wav done
parts/out000000025.wav started
parts/out000000020.wav done
parts/out000000021.wav started
parts/out000000032.wav done
parts/out000000033.wav started
parts/out000000028.wav done
parts/out000000029.wav started
parts/out000000008.wav done
parts/out000000009.wav started
parts/out000000016.wav done
parts/out000000017.wav started
parts/out000000012.wav done
parts/out000000013.wav started
parts/out000000005.wav done
parts/out000000006.wav started
parts/out000000025.wav done
parts/out000000026.wav started
parts/out000000033.wav done
parts/out000000034.wav started
parts/out000000009.wav done
parts/out000000010.wav started
parts/out000000029.wav done
parts/out000000030.wav started
parts/out000000017.wav done
parts/out000000018.wav started
parts/out000000013.wav done
parts/out000000014.wav started
parts/out000000021.wav done
parts/out000000022.wav started
parts/out000000006.wav done
parts/out000000035.wav started
parts/out000000026.wav done
parts/out000000039.wav started
parts/out000000034.wav done
parts/out000000043.wav started
parts/out000000018.wav done
parts/out000000047.wav started
parts/out000000022.wav done
parts/out000000051.wav started
parts/out000000030.wav done
parts/out000000055.wav started
parts/out000000010.wav done
parts/out000000059.wav started
parts/out000000014.wav done
parts/out000000063.wav started
parts/out000000039.wav done
parts/out000000040.wav started
parts/out000000035.wav done
parts/out000000036.wav started
parts/out000000043.wav done
parts/out000000044.wav started
parts/out000000055.wav done
parts/out000000056.wav started
parts/out000000051.wav done
parts/out000000052.wav started
parts/out000000047.wav done
parts/out000000048.wav started
parts/out000000059.wav done
parts/out000000060.wav started
parts/out000000044.wav done
parts/out000000045.wav started
parts/out000000040.wav done
parts/out000000041.wav started
parts/out000000063.wav done
parts/out000000064.wav started
parts/out000000036.wav done
parts/out000000037.wav started
parts/out000000056.wav done
parts/out000000057.wav started
parts/out000000048.wav done
parts/out000000049.wav started
parts/out000000060.wav done
parts/out000000061.wav started
parts/out000000045.wav done
parts/out000000046.wav started
parts/out000000052.wav done
parts/out000000053.wav started
parts/out000000037.wav done
parts/out000000038.wav started
parts/out000000057.wav done
parts/out000000058.wav started
parts/out000000041.wav done
parts/out000000042.wav started
parts/out000000064.wav done
parts/out000000065.wav started
parts/out000000038.wav done
parts/out000000067.wav started
parts/out000000049.wav done
parts/out000000050.wav started
parts/out000000042.wav done
parts/out000000071.wav started
parts/out000000046.wav done
parts/out000000075.wav started
parts/out000000053.wav done
parts/out000000054.wav started
parts/out000000065.wav done
parts/out000000066.wav started
parts/out000000058.wav done
parts/out000000079.wav started
parts/out000000061.wav done
parts/out000000062.wav started
parts/out000000067.wav done
parts/out000000068.wav started
parts/out000000071.wav done
parts/out000000072.wav started
parts/out000000075.wav done
parts/out000000076.wav started
parts/out000000054.wav done
parts/out000000083.wav started
parts/out000000050.wav done
parts/out000000087.wav started
parts/out000000079.wav done
parts/out000000080.wav started
parts/out000000066.wav done
parts/out000000091.wav started
parts/out000000062.wav done
parts/out000000095.wav started
parts/out000000068.wav done
parts/out000000069.wav started
parts/out000000072.wav done
parts/out000000073.wav started
parts/out000000076.wav done
parts/out000000077.wav started
parts/out000000095.wav done
parts/out000000096.wav started
parts/out000000080.wav done
parts/out000000081.wav started
parts/out000000087.wav done
parts/out000000088.wav started
parts/out000000083.wav done
parts/out000000084.wav started
parts/out000000069.wav done
parts/out000000070.wav started
parts/out000000091.wav done
parts/out000000092.wav started
parts/out000000073.wav done
parts/out000000074.wav started
parts/out000000077.wav done
parts/out000000078.wav started
parts/out000000096.wav done
parts/out000000097.wav started
parts/out000000084.wav done
parts/out000000085.wav started
parts/out000000088.wav done
parts/out000000089.wav started
parts/out000000081.wav done
parts/out000000082.wav started
parts/out000000070.wav done
parts/out000000099.wav started
parts/out000000092.wav done
parts/out000000093.wav started
parts/out000000074.wav done
parts/out000000103.wav started
parts/out000000085.wav done
parts/out000000086.wav started
parts/out000000097.wav done
parts/out000000098.wav started
parts/out000000078.wav done
parts/out000000107.wav started
parts/out000000099.wav done
parts/out000000100.wav started
parts/out000000089.wav done
parts/out000000090.wav started
parts/out000000082.wav done
parts/out000000111.wav started
parts/out000000093.wav done
parts/out000000094.wav started
parts/out000000103.wav done
parts/out000000104.wav started
parts/out000000098.wav done
parts/out000000115.wav started
parts/out000000086.wav done
parts/out000000119.wav started
parts/out000000100.wav done
parts/out000000101.wav started
parts/out000000090.wav done
parts/out000000107.wav done
parts/out000000108.wav started
parts/out000000119.wav done
parts/out000000111.wav done
parts/out000000112.wav started
parts/out000000094.wav done
parts/out000000115.wav done
parts/out000000116.wav started
parts/out000000104.wav done
parts/out000000101.wav done
parts/out000000105.wav started
parts/out000000102.wav started
parts/out000000108.wav done
parts/out000000109.wav started
parts/out000000112.wav done
parts/out000000113.wav started
parts/out000000116.wav done
parts/out000000117.wav started
parts/out000000105.wav done
parts/out000000106.wav started
parts/out000000102.wav done
parts/out000000109.wav done
parts/out000000110.wav started
parts/out000000113.wav done
parts/out000000114.wav started
parts/out000000106.wav done
parts/out000000117.wav done
parts/out000000118.wav started
parts/out000000110.wav done
parts/out000000114.wav done
parts/out000000118.wav done
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/speech_recognition/__init__.py", line 203, in __enter__
    self.audio_reader = wave.open(self.filename_or_fileobject, "rb")
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/wave.py", line 499, in open
    return Wave_read(f)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/wave.py", line 163, in __init__
    self.initfp(f)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/wave.py", line 130, in initfp
    raise Error('file does not start with RIFF id')
wave.Error: file does not start with RIFF id

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/speech_recognition/__init__.py", line 208, in __enter__
    self.audio_reader = aifc.open(self.filename_or_fileobject, "rb")
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 913, in open
    return Aifc_read(f)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 352, in __init__
    self.initfp(file_object)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 316, in initfp
    raise Error('file does not start with FORM id')
aifc.Error: file does not start with FORM id

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/speech_recognition/__init__.py", line 234, in __enter__
    self.audio_reader = aifc.open(aiff_file, "rb")
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 913, in open
    return Aifc_read(f)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 358, in __init__
    self.initfp(f)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/aifc.py", line 314, in initfp
    chunk = Chunk(file)
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/chunk.py", line 63, in __init__
    raise EOFError
EOFError

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File "fast.py", line 28, in <module>
    all_text = pool.map(transcribe, enumerate(files))
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/multiprocessing/pool.py", line 266, in map
    return self._map_async(func, iterable, mapstar, chunksize).get()
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/multiprocessing/pool.py", line 644, in get
    raise self._value
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/multiprocessing/pool.py", line 119, in worker
    result = (True, func(*args, **kwds))
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/multiprocessing/pool.py", line 44, in mapstar
    return list(map(*args))
  File "fast.py", line 18, in transcribe
    with sr.AudioFile(name) as source:
  File "/Library/Frameworks/Python.framework/Versions/3.6/lib/python3.6/site-packages/speech_recognition/__init__.py", line 236, in __enter__
    raise ValueError("Audio file could not be read as PCM WAV, AIFF/AIFF-C, or Native FLAC; check if file is corrupted or in another format")
ValueError: Audio file could not be read as PCM WAV, AIFF/AIFF-C, or Native FLAC; check if file is corrupted or in another format
```

Possible Solutions
* Notice that the first file it tries to read is a .DS_store...maybe that's the issue?
* Tried running this as python instead of python3 and it errored out almost immediately, again  starting with the .DS_store file.
* Tried running again as python3, again started with the .DS_store file, failed again with the same error messages.

Removed .DS_store file from folder


```python
cd parts
find . -name '.DS_Store' -type f -delete
```

Re-running file that has worked previously after troubleshooting
* Ran again using python3, this time it did not start with the .DS_store file, and completed successfully!

Running a completely new file
* manually cleared out the parts folder using Finder
* saved the previously created transcripts.txt folder under a new name and moved it to the transcripts folder
* ran ffmpeg


```python
ffmpeg -i source/[filename].wav -f segment -segment_time 30 -c copy parts/out%09d.wav
```

* ffmpeg successfully created 11 segments
* ran fast.py script
* successfully created transcript

Troubleshooting errors
* check for .DS_store file, doesn't seem to come back after it has been deleted unless you edit the folder with Finder...probably wouldn't have this problem if using straight CLI
* check for files without speach, static or silent files will crash transcription
* files shorter than 30 seconds will also crash transcription if ffmpeg has made them 30 seconds, they can be transcribed without using ffmpeg by moving them directly in to the parts folder
* look for files that have a much smaller file size to ID files with dead air in them...30 seconds of audio appears to be 5.3 MB
