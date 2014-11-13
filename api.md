# Karousel API Documentation

# Group Authentication

## Token Resource [/tokens/]

### Create New Token [POST]

+ Request

    + Headers

        Content-Type: application/json

    + Body

        {
            "username": "citruspi",
            "password": "secure123!"
        }

+ Response 201

    + Headers

        Content-Type: application/json

    + Body

        {
            "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw",
            "expires": "2009-11-10 23:00:00 +0000 UTC"
        }

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

# Group Users

## User Resource [/users/]

+ Model

    + Headers

            Content-Type: application/json

    + Body

            [
                {
                    "admin": false,
                    "gravatar": "gravatar.service@mihirsingh.com",
                    "id": 1,
                    "joined": "2009-11-10 23:00:00 +0000 UTC",
                    "username": "citruspi"
                }
            ]

### Get Users [GET]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [User Resource][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

### Create New User [POST]

+ Request

    + Headers

            Content-Type: application/json

    + Body

            {
                "username": "moti",
                "password": "secure123",
                "email": "moti@icloud.com"
            }

+ Response 201

    + Headers

            Content-Type: application/json
            Location: /users/:id

+ Response 400

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Incomplete request."
            }

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 409

    + Headers

            Content-Type application/json

    + Body

            {
                "error": "Duplicate resource."
            }

## User Instance [/users/{id}/]

+ Parameters

    + id (required, string, `1`)

+ Model

    + Headers

            Content-Type: application/json

    + Body

            {
                "admin": false,
                "gravatar": "gravatar.service@mihirsingh.com",
                "id": 1,
                "joined": "2009-11-10 23:00:00 +0000 UTC",
                "username": "citruspi",
            }

### Get User [GET]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [User Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

### Delete User [DELETE]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [User Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

# Group Collections

## Collection Resource [/collections/]

+ Model

    + Headers

            Content-Type: application/json

    + Body

            [
                {
                    "id": 1,
                    "name": "2014-2015",
                    "created": "2009-11-10 23:00:00 +0000 UTC",
                    "modified": "2009-11-10 23:00:00 +0000 UTC",
                    "size": 40
                }
            ]

### Get Collections [GET]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Collection Resource][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

### Create New Collection [POST]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

    + Body

            {
                "name": "2015-2016"
            }

+ Response 201

    + Headers

            Content-Type: application/json
            Location: /collections/:id

+ Response 400

    + Headers

            Content-Type: application/json

    + Body

            {
                "success": false,
                "error": "Incomplete form submission."
            }

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 409

    + Headers

            Content-Type application/json

    + Body

            {
                "error": "Duplicate resource."
            }

## Collection Instance [/collections/{id}/]

+ Parameters

    + id (required, string, `1`)

+ Model

    + Headers

            Content-Type: application/json

    + Body

            {
                "id": 1,
                "name": "2014-2015",
                "created": "2009-11-10 23:00:00 +0000 UTC",
                "modified": "2009-11-10 23:00:00 +0000 UTC",
                "albums": [
                    {
                        "id": 1,
                        "name": "Welcome Back",
                        "created": "2009-11-10 23:00:00 +0000 UTC",
                        "modified": "2009-11-10 23:00:00 +0000 UTC",
                        "size": 15
                    }
                ]
            }

### Get Collection [GET]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Collection Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

### Delete Collection [DELETE]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Collection Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

# Group Albums

## Album Resource [/albums/]

+ Model

    + Headers

            Content-Type: application/json

    + Body

            [
                {
                    "id": 1,
                    "name": "Welcome Back",
                    "created": "2009-11-10 23:00:00 +0000 UTC",
                    "modified": "2009-11-10 23:00:00 +0000 UTC",
                    "size": 15,
                    "collection": {
                        "id": 1,
                        "name": "2014-2015"
                    }
                }
            ]

### Get Albums [GET]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Album Resource][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

### Create New Album [POST]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

    + Body

            {
                "name": "Fall Camping",
                "collection": 1
            }

+ Response 201

    + Headers

            Content-Type: application/json
            Location: /albums/:id

+ Response 400

    + Headers

            Content-Type: application/json

    + Body

            {
                "success": false,
                "error": "Incomplete form submission."
            }

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 409

    + Headers

            Content-Type application/json

    + Body

            {
                "error": "Duplicate resource."
            }

## Album Instance [/albums/{id}/]

+ Parameters

    + id (required, string, `1`)

+ Model

    + Headers

            Content-Type: application/json

    + Body

            {
                "id": 1,
                "name": "Welcome Back",
                "created": "2009-11-10 23:00:00 +0000 UTC",
                "modified": "2009-11-10 23:00:00 +0000 UTC",
                "photos": [
                    {
                        "id": 1,
                        "name": "Welcome Back",
                        "uploaded": "2009-11-10 23:00:00 +0000 UTC"
                    }
                ],
                "collection": {
                    "id": 1,
                    "name": "2014-2015"
                }
            }

### Get Album [GET]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Album Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

### Delete Album [DELETE]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Album Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

# Group Photos

## Photo Resource [/photos/]

+ Model

    + Headers

            Content-Type: application/json


### Create New Photo [POST]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

    + Body

            {
                "album": 1,
                "file": (multipart upload)
            }

+ Response 201

    + Headers

            Content-Type: application/json
            Location: /photos/:id

+ Response 400

    + Headers

            Content-Type: application/json

    + Body

            {
                "success": false,
                "error": "Incomplete form submission."
            }

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 409

    + Headers

            Content-Type application/json

    + Body

            {
                "error": "Duplicate resource."
            }


## Photo Instance [/photos/{id}/]

+ Parameters

    + id (required, string, `1`)

+ Model

    + Headers

            Content-Type: application/json
    + Body

                {
                    "id": 1,
                    "name": "Welcome Back",
                    "uploaded": "2009-11-10 23:00:00 +0000 UTC",
                    "copies": {
                        "thumbnail": {
                            "resolution": {
                                "width": 100,
                                "height": 100
                            },
                            "id": 4
                        },
                        "original": {
                            "resolution": {
                                "width": 6000,
                                "height": 4000
                            },
                            "id": 1
                        },
                        ...
                    },
                    "exif": {
                        ...
                    }
                }

### Get Photo [GET]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Photo Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }

### Delete Photo [DELETE]

+ Request

    + Headers

        Content-Type: application/json
        X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [Photo Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }


# Group Files

## File Instance [/files/{id}/]

+ Parameters

    + id (required, string, `1`)

+ Model

    + Headers

            Content-Type: application/json
    + Body

            {
                "id": 1,
                "checksum": "bc819456266596e4fa51e5dc58dd9bef751597719f6d9b1917edb807dffe929c",
                "type": "photo",
                "parent": 1,
                "path": "/idontknow/downloadthisfile/blargh"
            }

### Get File [GET]

+ Request

    + Headers

            Content-Type: application/json
            X-Authentication-Token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmVzIjoxNDE2MDk1NjE3LCJ1c2VyX2lkIjoxfQ.Yk7M5n1zYBUci4kfk7FAh8hQz4-KHKEC8eMzam3mZXw

+ Response 200

    [File Instance][]

+ Response 401

    + Headers

        Content-Type application/json

    + Body

        {
            "error": "Invalid credentials."
        }

+ Response 404

    + Headers

            Content-Type: application/json

    + Body

            {
                "error": "Resource not found."
            }
