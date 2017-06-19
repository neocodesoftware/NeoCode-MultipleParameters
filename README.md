# NeoCode-MultipleParameters
use repeating fields and base64 for passing multiple parameters from client to server

# Use Case
for pre filemaker 16 solutions that don't have json - i built this to escape text - so you can pass an array to a server script

# File
sample solution - singe script that demonstrates packing and unpacking algorithm

security - user Admin / password [empty]

# Format
data structure - encode ( encode ( encode ( value1 ), value2 ), value3 )

so left hand is always encoded and right hand is decoded

# highlevel problem

server scripts run in their scope
they don't have access to variables

# actual problem

client needs to send email from filemaker client desktop that is outside lan

only computers on lan have access to to smtp server

solutions use filemaker psos to send server side email

# implementation problem

how to send mail envelope fields - to, from, subject, body, user, pass to psos

# new solution

make a global repeating field for array storage

populate repeating fields with values - scope client session

run solution package script to create base64 package of values

run email psos script with base64 package

run solution to unpackage values - scope server script session
