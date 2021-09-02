# JHANSI
THIS is my first API
openapi: 3.0.0
info:
  version: 1.0.0
  title: good profile
  description: This is personal profile details
  termsOfService: https://sample.com/tos
  contact:
    name: Lakshmi
    url: https://myserver.com
    email: Lakshmisri@gmai.com
  license:
    name: sample license
    url: https://license.sample.com
  servers:
    url: https://dev.sample.com/tos
    description: Dev server
  
    url: https://prod.sample.com
    description: prod server 
  paths:
    /v1/profile:
      get:
        description: This profile is about an person infomation
        summery: getprofile
        operationId: getAllprofiles
        parameters: 
          name: bodylimit
          in: query
          description: the profile is on returned
          schema: 
            type: integer
            minimum: 10
            maximum: 20
            example: 15
            name: pagelimit
            in: query
            description: The profile  returned
            schema:
              type: integer
              minimum: 1
              maximum: 5
              example: 3
              
      responses: 
        '200':
          description: Succesfully get profile info
          content: 
            application/json: 
              schema: 
                $refs: "#/components/schemas/profilebodylimit"
              example: 
                $refs: "#/components/sample/conformation-succes
      security: []
        post: 
         tags:
          /v1/profile
          summary: Create anew profile
          description: Add anew profile to the system
            operationId: postprofile
            requestbody:
               required: true
               content:
                 application/json:
                  schema: "#/components/schemas/profile"
      respones: 
        '201':
          description: profile created
          content: 
            application/json:
              schema:
                type: array
                iteams:
                  properties:
                    id: # it is an unique id
                      type: integer
                      format: uuid
                      description: uuid is a system generated value and its hard to gess the next one
                  schemas:
                    type: string
                    first name:
                       type: string
                       minlength: 2
                       maxlenght: 100
                       example: jhansilakshmi
                    lastname: 
                      type: string
                      minlength: 2
                      maxlength: 100
                      example: Ramisetty
                    age:
                      type: integer
                      fromate: int32
                      minimum: 0
                       
        '400':
          description: Bad request
      schemas:
        Address:
          type: object
          description: address object
          properties:
            street:
              type: string
              example: 420
            city:
              type: strimg
              example: Hyb
            zipcode:
              type: string
              example: 522004
            country:
              type: string
              example: India
              minlength: 2
              maxlength: 3
              description: 3 letter country code
              # enum: [USA, UK, IND, SA, NWL] one way hendle enum
              enum:
              - USA
              - UK
              - IND
              - NWL
              - AUS
