
<p align="center">
  <img width="500" alt="logo" src="https://raw.githubusercontent.com/Lekuruu/titanic/main/.github/logo/logo_medium.png">
</p>

# Titanic

Titanic is a private server made to be compatible with all osu! stable clients (2008-2024).
The goal of this project was to gain deeper insights into the inner functions of Bancho and how it changed over the years.

The main goal of this project was achieved. There are still some features that I want to add, which you can view [here](https://github.com/users/osuTitanic/projects/2).

You can play on it, by [registering on the website](https://osu.lekuru.xyz/account/register), and [downloading](https://osu.lekuru.xyz/download) a client from the website. **Keep in mind that only a smaller range of clients will be available there.**
For anyone interested, we also have a Discord server: https://discord.gg/qupv72e7YH

## Setup

To set up and use this project I would recommend to use [docker](https://www.docker.com/), as it's easier to set up in most cases. If you do not feel comfortable using docker, here are some instructions for the [manual setup](https://github.com/osuTitanic/titanic/blob/main/SETUP.md), which is not recommended but still possible to do.

Verify that docker is installed:

```shell
docker --version
```

Clone this project onto your machine:

```shell
git clone --recurse-submodules --shallow-submodules https://github.com/osuTitanic/titanic.git
```

Rename the `.example_env` to `.env` and **edit it**.

Start the server:

```shell
docker compose up -d
```

("-d" argument means detached, meaning that containers will run in background)

To turn off the server, from the titanic root folder, execute:

```
docker compose stop
```

If you changed some files around, and don't see your changes applied, execute:

```
(rebuild)
docker compose build
(apply changes & restart affected containers)
docker compose up -d
```

After the setup is done, you should have a PostgreSQL database instance, which you can access using your database management system of choice.
By default, it contains the user `peppy` with the password `recorderinthesandybridge`.

## Adding beatmaps

To add beatmaps, you will need to create them manually, inside the database, since the beatmap submission system is not implemented at the moment.

**However**, I have a small collection of beatmaps and beatmapsets that you can import to your database:

- [beatmapsets.sql.gz](https://github.com/osuTitanic/titanic/raw/main/migrations/beatmapsets.sql.gz)
- [beatmaps.sql.gz](https://github.com/osuTitanic/titanic/raw/main/migrations/beatmaps.sql.gz)

They are gzip-compressed sql files, which contain a total of 140k beatmaps from 2007-2013.

## Patching the client

You can view the instructions for patching the client [here](https://github.com/osuTitanic/clients/blob/main/PATCHING.md).

## Contributing

You are welcome to make any kinds of suggestions or contributions to this project.
Feel free to contact me if you have any questions.

## Credits

- [kanaarima](https://github.com/kanaarima/) for helping with the Discord bot & developing the pp system
- [osu.direct](https://osu.direct/) & [nerinyan.moe](https://nerinyan.moe/) for providing beatmap resources
- [rory](https://github.com/TheArcaneBrony) for [funny playtesting](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot022.jpg)
- Everyone that donated & contributed to this project (you guys are a big help!)

## Screenshots

#### b20130606.1

![sanic](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot007.jpg)
![cool](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot008.jpg)

#### b20130303

![wow](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot023.jpg)

#### b1700

![nice](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot005.jpg)
![multiplayer](https://raw.githubusercontent.com/osuTitanic/titanic/main/.github/images/screenshot006.jpg)
