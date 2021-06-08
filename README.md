<h1 align="center">
  Certificate Generator Serverless
</h1>

<p align="center">
  <a href="#-Technologies">Technologies</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#-Project">Project</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-Info">Info</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
    <a href="#memo-Certificate">Certificate</a>
</p>

<p align="center">
 <img src="https://img.shields.io/static/v1?label=PRs&message=welcome&color=49AA26&labelColor=000000" alt="PRs welcome!" />

  <img alt="License" src="https://img.shields.io/static/v1?label=license&message=MIT&color=49AA26&labelColor=000000">
</p>

<br>


## 🚀 Technologies

This project was developed with the following technologies:

- Typescript
- Serverless
- Dynamodb
- Puppetter
- chrome-aws and others


## 💻 Project

This project was created in the Ignite career accelerator program, it is based on two serverless functions that are hosted on AWS. Through these functions we can generate and verify PDF certificates. 


## :memo: Info

This project is basically divided into these two routes:

### Create Certificate (POST)
> https://pfmaxzpd0l.execute-api.sa-east-1.amazonaws.com/dev/generateCertificate

For this route we must pass the following parameters in the request body

```json
{
	"id": "7c74b700-0ea3-47b1-83d0-c68f0ca2d315",
	"name": "Samuel Paulo Stalschus",
	"grade": "10.00"
}
```
Return status 201
```json
{
  "message": "Certificate created!",
  "url": "https://ignitecertificatesmk.s3-sa-east-1.amazonaws.com/7c74b700-0ea3-47b1-83d0-c68f0ca2d315.pdf"
}
```
### Verify Certificate (GET)
> https://pfmaxzpd0l.execute-api.sa-east-1.amazonaws.com/dev/verifyCertificate/:id

Para essa rota passamos o id do usuário como parametro de rota para verificação de certificado. Podemos esperar dois retornos distintos

status 201
```json
{
  "message": "Certificado válido",
  "name": "Samuel Paulo Stalschus",
  "url": "https://ignitecertificatesmk.s3-sa-east-1.amazonaws.com/7c74b700-0ea3-47b1-83d0-c68f0ca2d315.pdf"
}
```
Or

status 400
```json
{
  "message": "Certificado inválido"
}
```


-------------------------------------------------------------------------------

## :memo: Certificate

<p align="center">
  <iframe alt="pdf" src="certificate.pdf" width="100%"></iframe>

</p>
