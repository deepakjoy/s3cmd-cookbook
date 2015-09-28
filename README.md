# s3cmd-cookbook
Useful commands for s3cmd

You'll find all basic commands on the s3cmd usage page: http://s3tools.org/usage

1. **List all files in a bucket (recursively)** <br>
   ```s3cmd --recursive ls s3://mybucket```
2. **List all files in a folder in a bucket (recursively)** <br>
   ```s3cmd --recursive ls s3://mybucket/folder1/folder2```
3. **Upload files with Cache-Content header from local folder to S3 folder (This is useful if you need to add headers to files)** <br>
   ```s3cmd put --recursive  setacl --acl-public --recursive --add-header='Cache-Control:max-age=2592000'  /myfolder2/  s3://mybucket/myfolder2/```
4. **Get number of files in a bucket** <br>
   ```3cmd ls --recursive s3://mybucket | wc -l``` <br>
   If you want to see the list, you can first pipe it to a file, and then count the lines. <br>
   ```s3cmd ls -r s3://mybucket/subfolder/ > listing.txt``` <br>
   ```wc -l listing.txt``` <br>
   Note: This command lists out all the files before counting, so if you have a large number of files, it may take a very long time. I tried with around 60k files, and it took a couple of minutes.
