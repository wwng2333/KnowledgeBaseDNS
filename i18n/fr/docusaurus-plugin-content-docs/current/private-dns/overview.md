---
title: Vue d'ensemble
sidebar_position: 1
---

:::info

Avec AdGuard DNS, vous pouvez configurer vos serveurs DNS privés pour résoudre les requêtes DNS et bloquer les publicités, les trackers et les domaines malveillants avant qu'ils n'atteignent votre appareil

Quick link: [Try AdGuard DNS](https://agrd.io/download-dns)

:::

![Tableau de bord AdGuard DNS privé principal](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/main.png)

## What is Private AdGuard DNS?

AdGuard DNS privé est un serveur DNS qui, en plus des avantages d'un serveur DNS public (tels que le cryptage du trafic et les listes de blocage de domaine), fournit des fonctionnalités comme la personnalisation flexible, les statistiques DNS et le contrôle parental, plus il est facilement géré via un tableau de bord pratique.

## Why you need Private AdGuard DNS

Aujourd'hui, vous pouvez connecter n'importe quoi à Internet : téléviseurs, réfrigérateurs, ampoules intelligentes ou haut-parleurs. Mais ces avantages indéniables s'accompagnent de traqueurs et de publicités. Un simple bloqueur de publicité basé sur un navigateur ne vous protégera pas dans ce cas, mais AdGuard DNS, que vous pouvez configurer pour filtrer le trafic, bloquer le contenu et les traqueurs, a un effet sur l'ensemble du système.

Nous avons déjà [AdGuard DNS public](../public-dns/overview.md) et [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome). Ces solutions conviennent à certains utilisateurs, mais pour d'autres, AdGuard DNS public manque de souplesse de configuration, tandis qu'AdGuard Home manque de simplicité. C'est là que AdGuard DNS privé entre en jeu. Il offre le meilleur des deux mondes : personnalisation, contrôle et information, le tout au moyen d'un tableau de bord simple et facile à utiliser.

## The difference between Private and Public AdGuard DNS

Voici une simple comparaison des fonctionnalités disponibles dans les serveurs AdGuard DNS Public et Privé.

| AdGuard DNS public                           | Private AdGuard DNS                                                                               |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Cryptage du trafic DNS                       | Cryptage du trafic DNS                                                                            |
| Listes de blocage de domaines prédéterminées | Listes de blocage de domaines personnalisables                                                    |
| -                                            | Règles de filtrage DNS personnalisées avec fonction d'importation/exportation                     |
| -                                            | Statistiques des requêtes (voir où vont vos requêtes DNS : quels pays, quelles entreprises, etc.) |
| -                                            | Journal de requêtes détaillé                                                                      |
| -                                            | Contrôle Parental                                                                                 |

## How to set up Private AdGuard DNS

1. Go to your [AdGuard DNS dashboard](https://agrd.io/download-dns) (if not logged in, log in using your AdGuard account)
1. Click "Connect device" and follow on-screen instructions

:::note Supported platforms:

- Android
- iOS
- Windows
- Mac
- Linux
- Routers
- Gaming consoles

:::

Every device that you add in the AdGuard DNS panel has its own unique address that can be used if the device supports modern encrypted DNS protocols (DoH, DoT, and DoQ).

## Linked IP

If the device does not support encrypted DNS and you have to use plain DNS, there's another way to allow AdGuard DNS to recognize the device — link its IP address. In this case AdGuard DNS counts all plain DNS requests that come from that IP address towards that "device".

The only requirement for linking IP is that **it must be a residential IP address**.

:::note

A residential IP address is an IP address assigned to a device connected to a residential ISP. It is typically associated with a physical location and is allocated to individual homes or apartments. Residential IP addresses are used by regular Internet users for their everyday online activities, such as browsing the web, accessing social media platforms, sending emails, or streaming content.

:::

If you're trying to link a residential IP address and AdGuard DNS does not allow you to do that, please contact our support team at support@adguard.com.

## Private AdGuard DNS features

### Blocklists management

With "Blocklists" feature you can set which domains you want to block and which you don't. Сhoose from wide variety of blocklists for different purposes.

![Private AdGuard DNS dashboard blocklists](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/blocklists.png)

### User rules

For times when pre-installed *Blocklists* with thousands of rules are not enough, we have a handy function called "User rules". Here you can add custom rules manually to block/unblock a certain domain or import custom rules lists (check out [DNS filtering rules syntax](../general/dns-filtering-syntax.md)). You can export the lists.

![Private AdGuard DNS dashboard user rules](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/import.png)

### Statistics

In "Statistics" tab you can see all the summarized statistics on DNS queries made by devices connected to your Private AdGuard  DNS. It shows the total number and geography of requests, the number of blocked requests, the list of companies the requests were addressed to, requests types and top requested domains.

![Private AdGuard DNS dashboard statistics](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/statistics.png)

### Traffic destination

This feature shows you where DNS requests sent by your devices go. On top of seeing the map of request destinations, you can filter the information by date, device and country.

![Private AdGuard DNS dashboard traffic](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/traffic_destination.png)

### Companies

This tab allows you to quickly check which companies send the most requests, and which companies have the most blocked requests.

![Private AdGuard DNS dashboard companies](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/companies.png)

### Query log

This is a detailed log where you can check out the information on every single request and also sort requests by status, type, company, device, time, country.

![Private AdGuard DNS dashboard query log](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/query_log.png)

### Contrôle Parental

To protect your child from online content you deem inappropriate, set up and activate the *Parental control* option. In addition to options such as "adult content" blocking and safe search, we've added the ability to manually specify domains for blocking and set a schedule for the *Parental control* to work accordingly.

![Private AdGuard DNS dashboard Parental Control](https://cdn.adtidy.org/public/Adguard/Blog/private_adguard_dns/parental_control.png)

In case you don't have Private AdGuard DNS yet, you can [get it on the official website](https://adguard-dns.io/).
