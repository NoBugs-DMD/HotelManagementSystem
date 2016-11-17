== Disclaimer ==
Server was built and tested in Gentoo GNU/Linux operating system with latest openssl libraries. 
Correct work in other environments is not guaranteed.

== Preparation ==
Install rust from https://www.rust-lang.org/en-US/downloads.html for your operating system.
Install the latest version of Google Chrome or Mozilla Firefox browser (IE/Edge is not supported).
Install PostgreSQL >9.5, create user, give him rights to create databases.

Fetch source code from Git repos:
> git clone git@github.com:NoBugs-DMD/HotelManagementSystemFrontend.git
> git clone git@github.com:NoBugs-DMD/HotelManagementSystemBackend.git

Edit HotelManagementSystemBackend/.env and setup previously prepared user credentials for PostgreSQL.
Install additional tools and follow instructions:
> cargo install just
> cargo install diesel

Setup database
> diesel database setup
> diesel migration run

== Build and Run ==
> just build-release
> just run-release

Run tool to populate database with >1000000 rows (can take a few hours).
> cd  HotelManagementSystemBackend/populate
> cargo run --release

Open HotelManagementSystemFrontend/index.html with your browser.