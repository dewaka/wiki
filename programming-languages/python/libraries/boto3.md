#  boto3 - Amazon Web Services SDK for Python

- Filtering AMIs based on tags,

  ```python
  ec2 = boto3.resource('ec2', region_name='us-east-1')
  filters = [{'Name': 'tag:Service', 'Values': ['your-tag']}]
  my_images = ec2.images.filter(Filters=filters)
  ```
