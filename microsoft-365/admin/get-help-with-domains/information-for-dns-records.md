---
title: DNS レコードを作成するために必要な情報を収集する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: ドメインをサブスクリプションに接続するために DNS レコードを作成するために必要な値Microsoft 365します。
ms.openlocfilehash: c56120e446ccde93d353bd4e36fd03493cda4688
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774450"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS レコードを作成するために必要な情報を収集する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>手順 1: TXT レコード値を検索して確認する

::: moniker range="o365-worldwide"

1. [ドメイン] Microsoft 365 管理センター[ドメイン]**ページ設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">移動</a>します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [ドメイン **] ページで** ドメインを選択し、[セットアップの開始] **を選択します**。 追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。
    
3. [ドメイン **検証] ページで** 、[ **ドメインの DNS** レコードに TXT レコードを追加する] を選択し、[続行] を **選択します**。
    
4. 表示されている **TXT 値をコピー** します。 **MS=msXXXXXXXX は次のように見えます**。 
    
5. [DNS レコード [の追加]](create-dns-records-at-any-dns-hosting-provider.md)に移動してドメインを接続し、DNS ホストの Web サイトでレコードを追加する手順に従います。
    
6. DNS ホストで TXT レコード (または MX レコード) を作成する手順に従って、ドメインをドメインに戻Microsoft 365。

7. ドメインがドメインで確認された後、DNS ホストから TXT レコード (または MX レコード) をMicrosoft 365。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>手順 2: メールの MX レコード値を検索する

::: moniker range="o365-worldwide"

1. [ドメイン] Microsoft 365 管理センター[ドメイン]**ページ設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">移動</a>します。

::: moniker-end
    
::: moniker range="o365-germany"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[設定]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end
    
2. [ **ドメイン**] ページで、ドメインを選びます。
    
3. [DNS **の管理]** を選択し、[その他 **のオプション]** 独自の DNS を追加し、[続行] を選択して追加する  >  DNS レコードを表示します。 
    
    DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。
    
    このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。
    
4. [DNS レコード [の追加]](create-dns-records-at-any-dns-hosting-provider.md)に移動してドメインを接続し、DNS ホストの Web サイトでレコードを追加する手順に従います。

5. 手順に従って、DNS ホストでレコードを作成します。

## <a name="related-content"></a>関連コンテンツ

[ドメインの FAQ](../setup/domains-faq.yml) (記事)\
[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)\
[ドメインの管理](index.yml) (リンク ページ)