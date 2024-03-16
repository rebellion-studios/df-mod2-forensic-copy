# df-mod2-forensic-copy

My task was to create fictional evidence files, and then duplicate them to create a sound copy to work with for file analyzation. The 1st evidence file shows a message about somebody claiming not to have sexual relations with somebody. The 2nd evidence file shows lyrics to a Monster High song. The 3rd evidence file shows the total budget and box office gross for the Scream movies. The 4th evidence file shows a quote from a certain horror icon. The 5th evidence file shows a bunch of years.

To obtain forensically sound files, I used the following code for each file. This copies everything in the chosen folder to a new location. Seperate hash files were added to the original folder as well as the new folder, before being combined into a single file.

```
Copy-Item "OLD-FOLDER\*" -Destination "NEW-FOLDER" -Recurse
```

To create hashes, the following code was used.

```
Get-FileHash PATH\evidence-new\evidence-#.txt | Out-File PATH\df-mod2-forensic-copy\evidence-new\hash-#.txt
```

## Hash

| File           | Original SHA-256                                                 | New SHA 256                                                      | Match? |
|----------------|------------------------------------------------------------------|------------------------------------------------------------------|--------|
| evidence-1.txt | F1F9B1C7931CEAAFF1C7D282613C751BB01B4CC02BF736A08D1611A7E02B9624 | F1F9B1C7931CEAAFF1C7D282613C751BB01B4CC02BF736A08D1611A7E02B9624 | Yes    |
| evidence-2.txt | B81B682FB254898119CEF6F4947E4C9614F29733488D37618BF6633C5AE46D32 | B81B682FB254898119CEF6F4947E4C9614F29733488D37618BF6633C5AE46D32 | Yes    |
| evidence-3.txt | 5DEDAB79F54D368E84D290114F188D7539FCAC1801077C712F6776BBFA51F52E | 5DEDAB79F54D368E84D290114F188D7539FCAC1801077C712F6776BBFA51F52E | Yes    |
| evidence-4.txt | 559FF8D5BF29E3139E8D27B7BFBA6F2068026E8AE634480B759233726CC9F250 | 559FF8D5BF29E3139E8D27B7BFBA6F2068026E8AE634480B759233726CC9F250 | Yes    |
| evidence-5.txt | 561E8FD4FCC77FF665019C3C0B82C2B6C390381F13D2D3748AEC6DBB05B291CF | 561E8FD4FCC77FF665019C3C0B82C2B6C390381F13D2D3748AEC6DBB05B291CF | Yes    |
