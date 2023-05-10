# GOLANG GRAPHQL MONGODB CRUD Project

##### Do the stuff below to initialize your project

1. Clone the repository
   `git clone https://github.com/Shittu24/go-graphQL-crud.git`
2. Change the directory
   `cd go-graphQL-crud`
3. Get all the dependencies
   `go mod tidy`
4. Run your project
   `go run main.go`
5. After you've written the graphql schema, run this - `go run github.com/shittu24/graphql-crud generate`
6. After you've built the project, these are the queries to interact with the API -

#### Get All Jobs

`query GetAllJobs{
  jobs{
    _id
    title
    description
    company
    url
  }
}`

=======================

#### Create Job

`mutation CreateJobListing($input: CreateJobListingInput!){
  createJobListing(input:$input){
    _id
    title
    description
    company
    url
  }
}`

{
"input": {
"title": "Software Development Engineer - I",
"description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt",
"company": "Google",
"url": "www.google.com/"
}
}`

=========================

#### Get Job By Id

`query GetJob($id: ID!){
job(id:$id){
_id
title
description
url
company
}
}`

`{
  "id": "638051d7acc418c13197fdf7"
}`

=========================

#### Update Job By Id

`mutation UpdateJob($id: ID!,$input: UpdateJobListingInput!) {
  updateJobListing(id:$id,input:$input){
    title
    description
    _id
    company
    url
  }
}`

`{
  "id": "638051d3acc418c13197fdf6",
  "input": {
    "title": "Software Development Engineer - III"
  }
}`

=================================

#### Delete Job By Id

`mutation DeleteQuery($id: ID!) {
  deleteJobListing(id:$id){
    deletedJobId
  }
}`

`{
  "id": "638051d3acc418c13197fdf6"
}`
