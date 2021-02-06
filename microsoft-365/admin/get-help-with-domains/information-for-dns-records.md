---
title: DNS レコードの作成に必要な情報を収集する
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
description: 'Microsoft 365 の DNS レコードを作成するために必要な値/情報を見つける方法について説明します。 '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126373"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS レコードの作成に必要な情報を収集する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>手順 1: TXT レコードの値を検索して確認する

::: moniker range="o365-worldwide"

1. Microsoft 365 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">に移動</a> します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[セットアップ ドメイン] **ページ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">に移動</a> します。

::: moniker-end
    
2. On the **Domains** page, select your domain, then select **Start setup**. 追加する必要がある特定の値を確認するには、ドメインのセットアップ ウィザードに戻ります。
    
3. [ドメイン **の確認] ページで** 、代わりに **[TXT レコード** の追加] を選択し、[次へ] を選択 **します**。
    
4. 表示された **TXT 値をコピー** します。 **MS=msXXXXXXXX**. 
    
5. 任意の DNS ホスティング [プロバイダーで DNS](create-dns-records-at-any-dns-hosting-provider.md)レコードを作成するに移動し、レジストラーの一覧から DNS ホストを選択して、詳しい手順を確認します。
    
6. DNS ホストで TXT レコード (または MX レコード) を作成する手順に従い、Microsoft 365 でドメインを確認します。

7. ドメインが Microsoft 365 で確認された後、DNS ホストから TXT レコード (または MX レコード) を削除します。
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>手順 2: メールの MX レコード値を検索する

::: moniker range="o365-worldwide"

1. Microsoft 365 管理センターで、[セットアップ ドメイン] **ページ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">に移動</a> します。

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
    
4. 任意の DNS ホスティング プロバイダーで [DNS](create-dns-records-at-any-dns-hosting-provider.md)レコードを作成するに移動し、レジストラーの一覧から DNS ホストを選択して、その DNS ホストの Web サイトでレコードを追加する手順を確認します。
    
5. 手順に従って、DNS ホストでレコードを作成します。
