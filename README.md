# Zeus

*This project is a POC. The objective here is to try to get an Elixir App which role is to collect files store them on the cloud. As this is a POC, no external calls will be made, instead, logs will show those attempts.*

## Requirements
* Elixir (>= 1.5.2)

## Usage
* `git clone git@github.com:BastienDuplessier/zeus.git`
* `cd zeus`
* `mix run --no-halt`

## Api

One endpoint only.

### POST `/collect` with
* user_id : Integer
* files : Array of File

`File` : Object(type, hour, part, checksum)
* Type : String
* Hour : String ("YYYY-MM-DD-HH")
* Part : Integer
* Checksum : String

#### Example
```Shell
 curl --request POST \
      --url http://localhost:5000/collector \
      --header 'content-type: application/json' \
      --data '{"user_id": "12","files": [{"type" : "france", "hour" : "2018-02-01-00", "part" : 0, "checksum" : "50256a2a22d455f77043d77ce57853ce"}, {"type" : "italy", "hour" : "2018-02-01-00", "part" : 0, "checksum" : "1e9d589335df71becf2bc8600cf1aca4"}]}'
```


