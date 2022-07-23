- 👋 Hi, I’m @cuttlfish
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
cuttlfish/cuttlfish is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

# dotnet certificates

For linux use these steps to create dev cert

dotnet dev-certs https -ep ~/.aspnet/https/aspnetapp.pem --format PEM
sudo cp ~/.aspnet/https/aspnetapp.pem /etc/ssl/certs/
sudo update-ca-certificates

With this running a simple web app will allow curl to work

# Simple webapp can be created
dotnet new webapp -n AspNetCoreDemo -o firstwebapp

This allows curl to access the https url of the webapp

# Linux http client 

Linux http client still has problem because in C# http client it doesn't look at
/etc/ssl/certs/ca.crt  when making request. Cert errors can be ignored by
overwriting ServerCertificateCustomValidationCallback and just returning
true even though there was an error


