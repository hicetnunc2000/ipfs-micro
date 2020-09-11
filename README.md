```
docker build -t ipfs-micro:latest .
docker run -d -p 3000:3000 ipfs-micro

heroku container:login
heroku create ipfs-micro
heroku container:push web --app ipfs-micro
heroku container:release web --app ipfs-micro

curl --header "Content-Type: application/json" --request POST --data '{"data": {"title":"title","description":"description"}}' http://ipfs-micro.herokuapp.com/post_json
{"hash":"QmP4Azn85QGrBXxzVkNAfFPS2a7hkE4uTdWxBE4TDErs1F"}

curl --header "Content-Type: application/json" --request POST --data '{"hash":"QmP4Azn85QGrBXxzVkNAfFPS2a7hkE4uTdWxBE4TDErs1F"}' http://ipfs-micro.herokuapp.com/get_json
{"data":{"title":"title","description":"description"}}

curl --header "Content-Type: application/json" --request POST --data '{"list": ["QmP4Azn85QGrBXxzVkNAfFPS2a7hkE4uTdWxBE4TDErs1F", "QmesAfkmnyofDHSudrAYBtYeBTdBkV1Ffi6fpvmaCXdnRV"]}' http://ipfs-micro.herokuapp.com/get_list
{"jsons":[{"data":{"title":"title","description":"description"}},{"data":{"title":"title2","description":"description2"}}]}




```

http://ipfs-micro.herokuapp.com/