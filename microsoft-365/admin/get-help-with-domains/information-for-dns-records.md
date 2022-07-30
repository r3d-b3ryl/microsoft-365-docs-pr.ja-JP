---
title: DNS レコードを作成するために必要な情報を収集する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: ドメインを Microsoft 365 サブスクリプションに接続するために DNS レコードを作成するために必要な値/情報を収集します。
ms.openlocfilehash: 653161734a8b0a2f188c8f8a54909ed86bf3fd5f
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084010"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS レコードを作成するために必要な情報を収集する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>手順 1: TXT レコードの値を見つけて確認する

::: moniker range="o365-worldwide"

1. Microsoft 365 管理センターで、[設定 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>**]** \> ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [ドメイン] ページ **で** ドメインを選択し、[セットアップの **開始**] を選択します。 追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。
    
3. **[ドメインの確認**] ページ **で、ドメインの DNS レコードに TXT レコードを追加するを** 選択し、[続行] を選択 **します**。
    
4. 表示されている **TXT 値** をコピーします。 MS **=msXXXXXXXX** は次のようになります。 
    
5. [[DNS レコードの追加] に移動してドメインを接続](create-dns-records-at-any-dns-hosting-provider.md)し、DNS ホストの Web サイトでレコードを追加する手順に従います。
    
6. DNS ホストで TXT レコード (または MX レコード) を作成する手順に従い、Microsoft 365 でドメインを確認します。

7. ドメインが Microsoft 365 で確認されたら、DNS ホストから TXT レコード (または MX レコード) を削除します。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>手順 2: 電子メールなどの MX レコード値を検索する

::: moniker range="o365-worldwide"

1. Microsoft 365 管理センターで、[設定 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>**]** \> ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [ **ドメイン**] ページで、ドメインを選びます。
    
3. [**DNS の管理**] を選択し、[**その他のオプション** > ] を選択 **して独自の DNS を追加** し、[**続行**] を選択して追加する DNS レコードを表示します。
    
    DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。
    
    このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。
    
4. [[DNS レコードの追加] に移動してドメインを接続](create-dns-records-at-any-dns-hosting-provider.md)し、DNS ホストの Web サイトでレコードを追加する手順に従います。

5. 手順に従って、DNS ホストでレコードを作成します。

## <a name="related-content"></a>関連コンテンツ

[ドメインの FAQ](../setup/domains-faq.yml) (記事)\
[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)\
[ドメインの管理](/admin) (リンク ページ)