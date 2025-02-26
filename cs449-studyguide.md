## Through the PRISM Darkly
1. What is the "false dilemma" mentioned in the article?
That if the NSA doesn't perform their surveillance there will be other terrorist attacks like 9/11.

2. Where should the real blame be placed regarding the Manning & Snowden leaks?
Whoever gave access to Manning/Snowden to access those classified documents. Based on Snowden's job title 
he did not need access to this documents.

3. What two defenses are used of the US surveillance program?
Trust me and false dilemma.

4. What are two myths concerning the surveillance program?
The first myth is that the goverment started (assulting the 4th Amendment) surveillance programs because of 9/11 when in fact they have been doing similar programs 
long before 9/11. The second is that there is rigorous oversight of surveillance activies (only through FISA which can be changed as seen fit by the government).

5. What is the primary oversight agency of the goverment surveilance program?
FISA

## "Free" Online Services and Gonzo Capitalism
1. In 2022 Google settled with forty states for $391.5 million. What was the charge against Google?
Google obfuscated their policy on personal location data collection.

2. The 2022 court settlement was based upon a 2018 expose by the Associated Press. What did the AP document expose?
Google services collected location data of iPhone and Android devices even if the user utilized settings that 
would prevent them from doing so.

3. What explanation did Google offer to justify the behavior documented by the Associated Press in 2018?
It was to improve personal experience.

4. What specific protections are there for personal privacy in the U.S. Consitution?
There is none. (This is why state laws on the matter are important)

5. According to the Supreme Court Justice William O. Douglas in Griswold v. Connecticut, any implied Constitutional guarantees 
of personal privacy would have to be found buried somehow in _______?
penumbra.

6. In 2023 the Department of Justice filed a second suit against Google for what crime?
For anticompetitive practices in its online advertising business.

7. In 2022 the U.S. House of Representatives Judiciary Committee published a report on competition in digital markets that listed 
several examples of illegal activities by online companies. List 2 of them.
Anticompetitive practices in online marketing and advertising.

8. The 2022 House report identified 3 common problems attributed to the four online platforms (Google, Amazon, Facebook, Apple). What are they?
- Platforms serve as gatekeepers over a key channel of distribution.
- Use gatekeeper position to maintain market power.
- Abuse their role as intermediaries to enrich themselves and dominate markets. 

9. The author lists 9 questionable business practices of Google that resulted from the recent international litigations. List 4 of them.
- misleading customers
- anticompetitive practices 
- blocking competition
- maintaining a monopoly
- illegally using captured biometric data
- creating an ecosystem of interlocked monopolies

10. What was the term that pioneers of modern economics Adam Smith and David Riccardo used to describe the business practices of which Google 
and other online platforms providers were accused in recent international courts?
Rent seeking

## Prosperity Theology Goes Online: Will This Be a Fifth Great Awakening?
1. What was the size of e-commerce annual revenue in 2021 according to Statistica.com?
$767 billion dollars

2. What does the acronym EULA stand for?
End User Licence Agreement

3. What does FBCP stand for?
Faith Based Content Provider

4. The article disccused several FBCPs. List two.
- Pray.com 
- Hallow.com
- BibleGateway.com 

5. List three "subsidiaries and affiliates" of BibbleGateway.com.
- Dow Jones 
- Realtor.com
- The Wall Street Journal 

6. What does B2C mean?
Business to Customer

7. Associate the FCBP businesses below with the appropriate property from the list. (a) B2C (b) subscription-based (c) registration-only fee-based 
- Hallow.com (b) subscription-based
- Pray.com (c) registration-only fee-based
- BibleGateway.com (a) B2C

8. Which FBCP includes the onerous "indemnification clause" in its EULA?
Pray.com

9. Which FBCP includes in its EULA a claim to freely use any IP disclosed in the use of the service?
BibleGateway.com

10. The author shares 10 observations relating to the evolution of FBCPs as of 2022. List 4 of them.
- FBCP have followed the path charted by e-commerce over the last 30 years by first experimenting with 
a free based service to determine a potential online presence then following that by identifying any lurking 
revenue streams.
- Could customer-to-customer business model succeed or be developed for FBCP.
- Social media is the perfect enviroment for cultivating, maintining, and manipulating thought bubbles and thought herds inside of them.
- To what extent will FBCP be able to take advantage of inderect revenues streams like pass-throughs. 


## BRAP Forensics
1. What is computer activity mining?
The recovery of information about a computer user or computer use throught the computer iteself, for example through system logs. 

2. List two core areas of modern computer forensics.
CAM (Computer Activity Mining) and media analysis.

3. What is media analysis/file system forensics?
Practice of recovering data from non-volatile storage devices.

4. What does BRAP forensics do?
Reveals stored data as well as information about user behavior.

5. Give two examples of BRAP forensics.
- Cookies on a browser which reveal user browing behavior (Browser Residue).
- Metadata on Microsoft Word which reveals the authors and changes to the file (Application Residue). 

6. Why were "cookies" developed? 
Because HTTP is stateless we use cookies to store information for subsequent requests.

7. In what file is the cache and URL history organized and stored on a Windows computer?
INDEX.DAT

8. What parts of the files are deleted when the recycle bin on a Windows computer is emptied?
The metadata.


## Data Hiding Tactics for Windows and Unix File Systems 
1. What were two early incarnations of data hiding metioned in the article?
- Storing data on out-of-standard track on a floppy disks that were beyond the reach of the operation system. 
- Hiding data in non-data fields in an network packet.

2. According to the article, hidden data may be thought of as a special case of what?
Intentionally dark data

3. What example given in the article of dark data that resides within light data?
Watermark

4. Provide two examples of non-physical data hiding?
- Cryptography 
- Watermarking 
- Steganography

5. What is the primary goal of cryptography?
Obscuring the content of the message and not the communication of the message.

6. What is the primary goal of steganography?
Concerned with hiding the communication of the message.

7. What is the primary goal of digital watermarking?
Add sufficient metadata to provide source, provenance, and ownership to a message.

8. The number of tracks/cylinders recognized by a disk controller has to be the same as the number of tracks/cylinders 
recognized by the operating system? (T/F)
False

9. What are the two structures of a hard disk drive?
Geometric structure and a set of nested data structures.

10. What is the name of the area of a secondary storage device where vendors could store data that is protected from normal user activities?
Host Protected Area

11. What is the feature that allows modification of the characteristics of a hard drive (e.g. the number of available clusters)?
Device Configuration Overlay

12. What is the name of the set of consecutive blocks on a hard disk that appear to an operating system as a seperate volume 
(aka, drive in Windows and directory/mount point in Unix)?
Partition

13. What is the name of the DOS partition at the beginning of a drive that contains the boot code and partition table?
Master Boot Record (MBR)

14. What is the name of the remaining area of a partition on a hard drive that cannot be accessed by the operating system by conventional means?
Volume slack

15. What is the name given to the unused sectors at the end of a partition that cannot be accessed by the operating system?
Partition slack 

16. Bad blocks/sectors are not accessible by the operating system? (T/F)
True

17. Hidden data may be store in bad blocks/sectors. (T/F)
True

 18. What is RAM slack?
 Data from memory that is added to pad the last sector when the file size does not take up an entire multiple of the sector.

 19. What is Microsoft's versions of a resource fork?
 Alternate Data Streams

 20. How long will an alternate data stream persist?
 For as long as the attached file or folder lives (assuming that file or folder lives and remains within a NTFS file structure)
 
 21. What is a file carver?
 Forensics tools that anaylze the data on a a drive without regarding the logical organization of the drive.

 22. Eleven digital disk warrens in Windows and Unix file systems were discussed in this article. List 5.
 - Hiding data within documents 
 - Hiding data within HTML
 - Encrypted files
 - Renamed files 
 - Binding one executable file to another

## Watermarking Cyberspace
1. What is a digital watermark?
A digital pattern or signal inserted into a digital document.

2. How does digital watermarking work?
The digital pattern or signal that is imposed on the digital document before being sold or 
distributed helps us authenticate the copies (giving the ability of ownership) of the document if the digital watermark is 
resilient against general transmissions and transformations. 

3. How does digital watermarking different from encryption?
Encryption makes a digital document not readable/usable until decrypted. A watermark does not do that instead it 
marks the document to authenticate the source (either in a visible or non visible manner). Plus encrytion does not leave 
any traces after being decrypted.

4. Give 3 examples of digital fingerprinting?
- Checksum algorithms 
- Cyclic redundancy 
- RSA message digest

5. Give 2 uses of digital watermarks?
- Watermarks can be used to check that a copy is authentic by removing the watermark and checking with a hashing algorithm 
that the watermakr is the same as the origal one created for the copy.
- Watermarks can have non-repudiable duplication by giving each copy that is being sent a different water mark so that if 
the copy is seen being disbributed without permission you can see which was the original copy that did it. 

6. What are the two main classes of digital watermarks?
- Visible
- Invisible

7. List two charactersctics of effective watermarks.
- Must be difficult or impossible to remove.
- Must survice common transmision and transformattions.

8. What are two main categories of watermarking techniques?
- Text 
- Image

9. What are two techniques for image watermarking?
- Color speration watermark so that the watermark only appears in a specific color band this technique is used for when journalist 
are selecting images to buy since the printer can not seperated the watermark.
- Frequency domain watermarking (FFT)

10. What are the three common techniques for watermarking text?
- Text-line coding 
- Word-space coding 
- Character encoding

## Disk Wiping by any other name 
1. What was the name of the builtin windows wiping utility? 
EFSTMPWP

2. How did the Windows cipher utility work?
It would write over very unallocated space. 

3. What was the problem with the Windows cipher utility?
It would take up so much space that the OS would hang up.

4. Windows doesn't delete file data. What doe it do when the delete file command is executed?
It marks the space the file was utlizing as unallocated so it can be used again.

5. What are the two problems caused when a disk sanitizer fails to overwrite the old MFT entries?
- The name of the old file is still available 
- If the file data was small enough it can be present and stored in the MFT

6. Of the seven disk whiping utilities analyzed, how many were shown to be effective?
One

7. Were the majority of disk wiping utilities effective at removing small datafiles that were present in the MFT entries?
No 

8. What is the term used to describe data that was unaffected by the disk wiping?


9. Why do disk wiping utilities frequently miss small files stored in MFT entries?
The MFT entries are labelled as allocated space which is not checked by disk wipers. 

10. Do disk wiping utilities clean the registry hive?
No 

11. What is the other category of utilities that are designed to used prior to reporpousing or recycling a drive?
Disk purgers

## Identity Theft and Financial Fraud: Some Strangeness in the Proportions 
1. What are 3 major causes or sources of financial fraud and identity theft?
- Lost/stolen devices 
- Hacked computers/computer network's
- Discarded/stolen documents

2. Which organizations have produced the lion's share of data breaches?
- Banks 
- Colleges 
- Govenment agencies 
- Healthcare providers
