---
title: ドメイン レジストラーを検索する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC 検索を使用して、ドメイン レジストラーと DNS ホスティング プロバイダーを探す方法を説明します。
ms.openlocfilehash: 2bfb4fc831d23751ab558dd833c49f84cb17c4c5
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67086410"
---
# <a name="find-your-domain-registrar"></a>ドメイン レジストラーを検索する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。

## <a name="domain-registrar"></a>ドメイン レジストラー

### <a name="find-your-domain-name-registrar"></a>ドメイン名登録業者を探す

> [!NOTE]
> *.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。

1. [InterNIC の検索ページ](https://go.microsoft.com/fwlink/p/?LinkId=402770)の [**Whois Search**] ボックスに、ドメインを入力します。たとえば、*contoso.com のように入力します。*

2. [**Domain**] オプションを選択し、[**Submit**] を選択します。

3. [**Whois Search Results**] ページで [**Registrar**] エントリを探します。このエントリには、ドメインに対してレジストラー サービスを提供している組織が表示されます。

## <a name="dns-hosting-provider"></a>DNS ホスティング プロバイダー

### <a name="find-your-dns-hosting-provider"></a>DNS ホスティング プロバイダーを探す

> [!NOTE]
> *.COM*、*.NET*、および *.EDU* で終わるドメインのみがこのツールで動作します。

1. [InterNIC の検索ページ](https://go.microsoft.com/fwlink/p/?LinkId=402770)の [**Whois Search**] ボックスに、ドメインを入力します。たとえば、contoso.com のように入力します。

2. [**Domain**] オプションを選択し、[ **Submit**] を選択します。

3. [**Whois Search Results**] ページで最初の [**Name Server**] エントリを探します。

4. コロン (:) の後に表示されるネーム サーバー (NS) 情報をコピーし、ページの先頭にある [**Search**] ボックスに貼り付けます。[**Nameserver**] を選択し、[**Submit**] を選択します。

5. [**Whois Search Results**] ページで [**Registrar**] エントリを探します。このエントリには、DNS ホスティング プロバイダー (ドメインのネーム サーバーを所有している DNS プロバイダー) が表示されます。

---

