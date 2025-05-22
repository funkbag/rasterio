FROM public.ecr.aws/lambda/python:3.9

# Install system packages
RUN yum install -y gcc gdal gdal-devel python3-devel libcurl-devel zip

# Install rasterio + numpy into the Lambda layer path
RUN pip3 install rasterio==1.2.10 numpy==1.23.5 -t /opt/python

# Strip binary size
RUN find /opt/python -name "*.so" -exec strip {} \;

