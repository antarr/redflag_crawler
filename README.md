# DJANGO IMAGE ANALYZER

This is a Django application that provides an API for analyzing images from a social network. It includes a crawler that can search for up to 5 images by keyword, and a machine learning model for performing analysis on the images.

## Prerequisites

This application requires Python 3 and the following packages:

- Django
- Requests
- Scikit-Learn

## Installation

Clone this repository:

```
$ git clone https://github.com/antarr/reflag_crawler.git
```

Install the required packages:

```
$ pip install -r requirements.txt
```

## Usage

Run the Django development server:

```
$ python manage.py runserver
```

The API is now accessible at http://127.0.0.1:8000.

### Endpoints

#### Search by keyword

This endpoint searches a social network for up to 5 images by keyword, and then performs machine learning analysis on the images.

Request:

```
GET http://127.0.0.1:8000/api/v1/search?keyword=<KEYWORD>
```

Response:

```
{
  "results": [
    {
      "image_url": <URL>,
      "analysis": {
        ...
      }
    },
    ...
  ]
}
```

#### Upload image

This endpoint directly uploads an image and performs machine learning analysis on it.

Request:

```
POST http://127.0.0.1:8000/api/v1/upload
```

With the image file in the request body.

Response:

```
{
  "image_url": <URL>,
  "analysis": {
    ...
  }
}
```