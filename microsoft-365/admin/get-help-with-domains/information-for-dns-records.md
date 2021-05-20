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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: ドメインをサブスクリプションに接続するために DNS レコードを作成するために必要な値Microsoft 365します。
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582958"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS レコードを作成するために必要な情報を収集する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>手順 1: TXT レコード値を検索して確認する

::: moniker range="o365-worldwide"

1. 管理センター Microsoft 365、[セットアップ ドメイン]**ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a>します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。

::: moniker-end
    
2. [ドメイン **] ページで** ドメインを選択し、[セットアップの開始] **を選択します**。 追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。
    
3. [ドメインの **確認] ページで** 、代 **わりに [TXT レコードの** 追加] を選択し、[次へ] を **選択します**。
    
4. 表示されている **TXT 値をコピー** します。 **MS=msXXXXXXXX は次のように見えます**。 
    
5. [任意の [DNS ホスティング](create-dns-records-at-any-dns-hosting-provider.md)プロバイダーで DNS レコードを作成する] に移動し、レジストラーの一覧から DNS ホストを選択して、詳細な手順を確認します。
    
6. DNS ホストで TXT レコード (または MX レコード) を作成する手順に従って、ドメインをドメインに戻Microsoft 365。

7. ドメインがドメインで確認された後、DNS ホストから TXT レコード (または MX レコード) をMicrosoft 365。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>手順 2: メールの MX レコード値を検索する

::: moniker range="o365-worldwide"

1. 管理センター Microsoft 365、[セットアップ ドメイン]**ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a>します。

::: moniker-end
    
::: moniker range="o365-germany"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。

::: moniker-end
    
2. [ **ドメイン**] ページで、ドメインを選びます。 
    
3. [ **必要な DNS 設定**] に、追加する DNS レコードが表示されます。
    
    DNS ホストで変更を行う際もこの情報を使用できるように、値をコピーして貼り付けることができます。
    
    このページにリストされる DNS レコードのグループは、[ **ドメインの目的**] における選択によって変わります。
    
4. [任意の DNS ホスティング プロバイダーで [DNS](create-dns-records-at-any-dns-hosting-provider.md)レコードを作成する] に移動し、レジストラーの一覧から DNS ホストを選択すると、その DNS ホストの Web サイトでレコードを追加する手順が詳細に表示されます。
    
5. 手順に従って、DNS ホストでレコードを作成します。

## <a name="related-content"></a>関連コンテンツ

[ドメインに関する FAQ](../setup/domains-faq.yml) (記事)

[ドメインまたは DNS レコードを追加後に問題を特定して解決する](find-and-fix-issues.md) (記事)

[ドメインの管理](index.yml) (リンク ページ)