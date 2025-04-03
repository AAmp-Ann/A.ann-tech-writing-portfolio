# How to Make a GCP Cloud Storage Bucket Public Using the CLI

This guide walks you through making a Google Cloud Storage bucket publicly accessible using the `gsutil` command line tool.

> **Warning:** Making a bucket public allows anyone on the internet to access the files inside. Use with caution.

## Prerequisites 

- A Google Cloud Account
- `gsutil` installed and authenticated via the Cloud SDK
- An existing bucket

## Steps

1. **Authenticate with Google Cloud**
```
gcloud auth login
```

2. **List Your Buckets**  
```
gsutil ls
```
Make sure the bucket you want to update appears in the list.

3. **Make the Bucket Public**
```
gsutil iam ch allUsers:objectViewer gs://[YOUR_BUCKET_NAME]
```
Replace [YOUR_BUCKET_NAME] with the name of your bucket.This grants read access to anyone on the internet.

4. **Verify Public Access**
   
Use the format to access a file publicity:
```
https://storage.googleapis.com/[YOUR_BUCKET_NAME]
```


## Next Steps

- Revoke public access when no longer needed.
- Use signed URLs for limited time access to specific files

---



