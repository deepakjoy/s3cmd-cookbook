# s3cmd-cookbook
Useful commands for s3cmd

You'll find all basic commands on the s3cmd usage page: http://s3tools.org/usage

1. **List all files in a bucket (recursively)** <br>
   ```s3cmd --recursive ls s3://mybucket```
2. **List all files in a folder in a bucket (recursively)** <br>
   ```s3cmd --recursive ls s3://mybucket/folder1/folder2```
3. **Upload files with Cache-Content header from local folder to S3 folder (This is useful if you need to add headers to files)** <br>
   ```s3cmd put --recursive  setacl --acl-public --recursive --add-header='Cache-Control:max-age=2592000'  /myfolder2/  s3://mybucket/myfolder2/```
