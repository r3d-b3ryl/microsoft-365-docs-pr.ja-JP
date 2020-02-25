---
title: Office 365 の DNS レコードの作成に必要な情報を収集する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Office 365 の DNS レコードを作成するために必要な値と情報を検索する方法について説明します。 '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255085"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>Office 365 の DNS レコードの作成に必要な情報を収集する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>手順 1: TXT レコード値を検索して確認する

1. Microsoft 365 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。
    
    Office 365 Germany を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>] ページに移動します。 
    
    21Vianet が運営する Office 365 を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>] ページに移動します。
    
2. [**ドメイン**] ページで、ドメインを選択し、[**セットアップの開始**] を選択します。 追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。
    
3. [**ドメインの確認**] ページで、[**代わりに TXT レコードを追加する**] を選択し、[**次へ**] を選択します。
    
4. 表示されている**TXT 値**をコピーします。 次のようになります。 **MS = msXXXXXXXX**。 
    
5. 「[任意の dns ホスティングプロバイダーで dns レコードを作成](create-dns-records-at-any-dns-hosting-provider.md)する」に移動し、レジストラーのリストから dns ホストを選択し、手順を追って説明します。
    
6. DNS ホストで TXT レコード (または MX レコード) を作成する手順を実行し、Office 365 でドメインを確認します。

7. Office 365 でドメインが検証されたら、DNS ホストから TXT レコード (または MX レコード) を削除します。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>手順 2: メールの MX レコード値を検索する

1. Microsoft 365 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。
    
    Office 365 Germany を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">ドメイン</a>] ページに移動します。 
    
    21Vianet が運営する Office 365 を使用している場合は、この [<a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">ドメイン</a>] ページに移動します。
    
2. [ **ドメイン**] ページで、ドメインを選びます。 
    
3. [ **必要な DNS 設定**] に、追加する DNS レコードが表示されます。
    
    DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。
    
    このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。
    
4. 「[任意の dns ホスティングプロバイダーで dns レコードを作成](create-dns-records-at-any-dns-hosting-provider.md)する」に移動して、レジストラーのリストから dns ホストを選択し、その dns ホストの web サイトにレコードを追加するための手順を順を追って説明します。
    
5. 手順に従って、DNS ホストでレコードを作成します。
