FROM python:3.9-alpine

EXPOSE 8080

# Create a non-root user and set it for the app
RUN adduser -D appuser
USER appuser

WORKDIR /app

# Copy only requirements.txt first for caching purposes
COPY requirements.txt /app/
RUN apk --no-cache add build-base linux-headers
RUN pip install --upgrade setuptools
RUN pip install --no-cache-dir -r requirements.txt

# Copy application files
COPY *.py /app/
COPY payment.ini /app/

# Set environment variables
ENV AMQP_USER=roboshop \
    AMQP_PASS=roboshop123

# Run the app using uWSGI
CMD ["uwsgi", "--ini", "payment.ini"]

