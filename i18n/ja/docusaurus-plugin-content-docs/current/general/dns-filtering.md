---
title: DNSフィルタリング
sidebar_position: 1
---

:::info

DNSフィルタリングのメリットを実感するための一番簡単な方法は、AdGuard 広告ブロッカーをインストールするか、AdGuard DNS を試してみることです。 そして、ネットワークレベルでDNSフィルタリングしたい場合は、AdGuard Home が最適です。

Quick links: [Download AdGuard Ad Blocker](https://agrd.io/download-kb-adblock), [Get AdGuard Home](https://github.com/AdguardTeam/AdGuardHome#getting-started), [Try AdGuard DNS](https://agrd.io/download-dns)

:::

DNSフィルタリングをよりよくご理解いただけるよう、まず「DNSとは何か」ということを説明したいと思います。

## 「DNS」とは？

DNSは「Domain Name System」（ドメイン・ネーム・システム）の略であり、その目的は、Webサイトの名前をブラウザが理解できるもの（IPアドレス）に変換することです。 つまり、各ウェブサイトにアクセスするたびに、ブラウザは特種のサーバー（DNSサーバー）にリクエストを送信します。 そのサーバーはリクエストされたドメイン名を調べ、対応するIPアドレスを返信します。 このプロセスを簡単な図に表すとこうなります：

![DNS の仕組み](https://cdn.adtidy.org/public/Adguard/kb/DNS_filtering/how_dns_works_en.png)

もちろん、ブラウザだけでなく、ウェブリクエストを送信するアプリやプログラムのすべてが同じようなプロセスになります。

## DNSフィルタリングの仕組み

DNSフィルタリングをサポートする AdGuard アプリを使用すると、AdGuard アプリはデバイスとDNSサーバーの間のバッファ（仲介）として機能します。 デバイス上のブラウザやアプリが送信しようとするすべてのDNSリクエストは、まずAdGuardによって処理されます。 ISP（インターネットプロバイダ）が提供するデフォルトDNSサーバーを使用している場合、DNSトラフィックは暗号化されていない可能性が高く、スヌーピングやハイジャック（傍受）に対して脆弱になります。 AdGuard は、DNSリクエストがデバイスから送信される前にすべて暗号化し、悪意のある第三者がその内容にアクセスできないようにします。 その上、AdGuardは、広告、トラッキング（追跡）、またはアダルトドメインへのリクエストを識別し、DNSサーバーに転送する代わりに「ブラックホール」にリダイレクトすることができます。 （これについては[以下で](#ローカルDNSブロックリスト)説明しております。）

![DNSフィルタリングの仕組み](https://cdn.adtidy.org/public/Adguard/kb/DNS_filtering/how_dns_filtering_works_ja.png)

DNSフィルタリングはパワフルなツールであり、AdGuardの全アプリ（[AdGuard for Windows](https://adguard.com/adguard-windows/overview.html), [AdGuard for Mac](https://adguard.com/adguard-mac/overview.html), [AdGuard for Android](https://adguard.com/adguard-android/overview.html), [AdGuard for iOS](https://adguard.com/adguard-ios/overview.html)）で、「DNS通信を保護」機能という形で利用可能です。

DNSフィルタリングは、2つの機能に分けることができます。DNSトラフィックを暗号化してDNSサーバーにリルーティングする機能と、DNSブロックリストを適用して一部のドメインをローカルでブロックする機能です。

### DNSサーバー

DNSサーバーは何千もあって、それぞれ特性と目的においてユニークであります。 多くは単にリクエストされたドメインのIPアドレスを返すだけですが、広告、トラッキング、アダルトドメインなどをブロックする追加機能を持つものもあります。 現在、一般的なDNSサーバーのすべては、信頼できる暗号化プロトコル（DNS-over-HTTPS、DNS-over-TLS）を1つ以上採用しています。 AdGuard も[DNSサービス](https://adguard-dns.io/)を提供しており、非常に新しく有望な [DNS-over-QUIC](https://adguard.com/blog/dns-over-quic.html) 暗号化プロトコルを世界で初めて採用したDNSとなりました。 AdGuard は目的別に複数のDNSサーバーを用意しています。 以下の図は、AdGuardのブロッキングサーバーの仕組みを示しています:

![AdGuard DNS](https://cdn.adtidy.org/public/Adguard/kb/DNS_filtering/adguard_dns_en.jpg)

他のDNSプロバイダーの仕組みは違ったりするので、それらのDNSサーバーを使う前に、プロバイダーや仕組みについての情報を確認しておいてください。 [こちらの記事](dns-providers.md)で、最も人気のあるDNSプロバイダーの一覧を確認することができます。 DNS機能のあるAdGuardアプリはすべて、人気DNSサーバーのリストを備えており、さらにニーズに応じてカスタムDNSサーバーをご自身で追加することもできます。

### ローカルDNSブロックリスト

しかし、DNSトラフィックをフィルタリングするためにDNSサーバーだけに頼ることは、柔軟性を失うことになります。 使っているサーバーがドメインをブロックしている場合、そのドメインにアクセスできません。 AdGuard ですと、DNSトラフィックをフィルタリングするために特定のDNSサーバーを設定する必要もありません。 AdGuard 製品のすべてで、DNS ブロックリスト（シンプルな hosts ファイルや[より高度な構文](dns-filtering-syntax.md)を使用するリストなど）を使用できます。 DNSブロックリストは、通常のブロックリストと同じように機能します。つまり、DNSリクエストがアクティブフィルタリストのルールの1つにマッチすると、そのリクエストはブロックされます。 より正確に言いますと、そのリクエストは"ブラックホール"に迂回されます。

:::tip

In AdGuard for iOS, first you have to enable *Advanced mode* in settings in order to get access to DNS blocking.

:::

You can add as many custom blocklists as you wish. For instance, you can use [AdGuard DNS filter](https://github.com/AdguardTeam/AdGuardSDNSFilter). It quite literally blocks everything that AdGuard DNS server does, but in this case you are free to use any other DNS server. Plus, this way you can add more filters or create custom exception rules, all of which would be impossible with a simple "use a blocking DNS server" setup.

There are hundreds of different DNS blocklists, you can look for them [here](https://filterlists.com/).

## DNSフィルタリングとネットワークフィルタリングの比較

Network filtering is what we call the 'regular' way AdGuard standalone apps process network traffic, hence the name. Feel free to brush up on it by reading [this article](https://adguard.com/kb/general/ad-filtering/how-ad-blocking-works/).

First of all, we have to mention that with AdGuard you don't have to choose. You can always use both regular network filtering and DNS filtering at the same time. However, it's important to understand key differences between the two. DNS filtering has both its unique advantages and drawbacks:

**Pros of DNS filtering:**

1. プラットフォームによっては、これがシステム全体フィルタリングを実現する唯一の方法です。 例えば、iOSではSafariブラウザだけが、コンテンツ・ブロッキングをサポートしています。Safari以外にはDNSフィルタリングしか使えません。
1. トラッキング（追跡）の一部（ [CNAMEトラッキング](https://adguard.com/blog/cname-tracking.html)など）は、DNSフィルタリングによってのみ防止できます。
1. DNSリクエストを処理する段階は、広告やトラッカーに対処する場合の最も早い段階であるため、バッテリー寿命とトラフィックを少し節約するのに役立ちます。

**Cons of DNS filtering:**

1. DNS filtering is "rough", meaning that it won't remove whitespaces that are left behind a blocked ad, or apply any sorts of cosmetic filtering. Many of the more complicated ads can't be blocked on DNS-level (or rather, they can, but only by blocking the entire domains which are being used for other purposes).

    ![Example of difference](https://cdn.adtidy.org/public/Adguard/kb/DNS_filtering/dns_diff.jpg) *An example of the difference between DNS filtering and network filtering*

1. It's not possible to know the origin of a DNS request, which means you can't distinguish between different apps on the DNS-level. This impacts the statistics negatively and makes it impossible to create app-specific filtering rules.

We recommend using DNS filtering in addition to network filtering, not instead of it, whenever possible.
