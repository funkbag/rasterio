FROM public.ecr.aws/lambda/python:3.9

# Install system packages for rasterio and numpy
RUN yum install -y gcc gdal gdal-devel python3-devel libcurl-devel zip

# Install rasterio and numpy into Lambda layer directory
RUN pip3 install rasterio==1.2.10 numpy==1.23.5 -t /opt/python

# Shrink size by stripping binaries
RUN find /opt/python -name "*.so" -exec strip {} \;

# Package the layer
RUN cd /opt && zip -r9 /workspace/rasterio-layer.zip python
