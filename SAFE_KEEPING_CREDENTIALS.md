# Best Practices to Safeguard Your Credentials

- Keep your credentials.env one directory level above your GitHub tree, so GitHub can never see it.
- Red Hat team updated the osc_ingest_tools library to provide an interface that doesn't even mention credentials.env:
- From the AWS Account page, copy the export scripts from the appropriate role using the "Command Line or Programmatic Access" link
- Paste the copied text into ~/credentials.env
- Load environment variables from credentials.env
  load_credentials_dotenv()

  From there, secrets appears by magic:

  s3_source = boto3.resource(

        service_name="s3",
        endpoint_url=os.environ['S3_LANDING_ENDPOINT'],
        aws_access_key_id=os.environ['S3_LANDING_ACCESS_KEY'],
        aws_secret_access_key=os.environ['S3_LANDING_SECRET_KEY'],

  )
  bucket = s3_source.Bucket(os.environ['S3_LANDING_BUCKET'])
