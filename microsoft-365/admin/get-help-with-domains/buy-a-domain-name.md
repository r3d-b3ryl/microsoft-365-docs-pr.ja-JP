---
title: ドメイン名を購入する
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1561140a-16a9-4a02-822d-a989250e479d
description: Microsoft 365 でドメイン名を購入する方法について説明します。
ms.openlocfilehash: 2f238698892e1a1d97c7d50fdad281e8973cb515
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085183"
---
# <a name="buy-a-domain-name"></a>ドメイン名を購入する

> [!NOTE]
> 組織が中国で 21Vianet によって運営されているOffice 365を使用している場合は、「中国の [21Vianet が運営するOffice 365のドメインを購入する方法](#how-to-buy-a-domain-for-office-365-operated-by-21vianet)」を参照してください。

 *ドメインを追加、変更、または削除するには、[ビジネスプランまたはエンタープライズ プラン](https://products.office.com/business/office)の **グローバル管理者** である **必要があります**。これらの変更は、テナント全体、*カスタマイズされた管理者*、または *通常のユーザー* がこれらの変更を行うことができなくなります。*  

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 
  
## <a name="sign-in-and-go-to-settings--domains--buy-a-domain"></a>サインインして [設定ドメイン] \> に移動する ドメインを購入する\>

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。
    
3. [ **ドメイン] ページで** 、[ **ドメインの購入**] を選択します。
    
ドメインには、次の最上位レベルのドメインから選択できます。
  
- .biz
    
- .com
    
- .info
    
- .me
    
- .mobi
    
- .net
    
- .org
    
- .tv
    
- .co.uk
    
- org.uk
    

> [!NOTE]
> **[ドメインの購入**] を選択すると、テナントが Microsoft パートナーを通じて購入または管理されている場合、Microsoft パートナーの Web サイトにリダイレクトされることがあります。

## <a name="domain-privacy"></a>ドメインのプライバシー
ドメインを購入すると、無料の Domain Privacy サブスクリプションが提供されます。 これにより、ICANN プライベートを使用してドメインの登録に連絡先情報が添付されます。 [詳細情報](https://whois.icann.org/en/privacy-and-proxy-services)
  
## <a name="buy-a-domain-from-another-domain-registrar"></a>別のドメイン レジストラーからドメインを購入する
[GoDaddy](https://www.godaddy.com) 以外のドメイン レジストラーからドメインを購入する場合は、自動セットアップ (Domain Connect) をサポートするドメイン レジストラーを使用することをお勧めします。 
  
- [1&amp;1 IONOS](https://www.1and1.com/)
- [WordPress](https://www.wordpress.com) 

   
## <a name="transfer-your-domain-to-a-different-domain-registrar"></a>ドメインを別のドメイン レジストラーに移行する

必要な DNS レコードの一部をサポートしていないプロバイダーがドメインを管理している場合は、ドメインを別のレジストラーに移行することができます。ドメインを移行するときには、ドメイン名の更新と保持のために支払先を変更します。
  
ドメインの移行先レジストラーに移行をリクエストします。 **DNS の移行** などのオプションについては、そのレジストラーの Web サイトでお確かめください。 変更を加えた後、インターネット経由で更新されるまでに数日かかる場合があります。

::: moniker range="o365-21vianet"

## <a name="how-to-buy-a-domain-for-office-365-operated-by-21vianet"></a>21Vianet が運営する Office 365 のドメインを購入する方法

専用ドメインをまだ持っていない場合は、ドメイン名レジストラー、ドメイン リセラー、現在のインターネット プロバイダーなどからオンラインで簡単に購入できます。21Vianet が運営する Office 365 にサインアップすると、たとえば、contoso.partner.onmschina.cn のようなドメイン名を与えられますが、fourthcoffee.com のようなカスタム ドメイン名を使うこともできます。
  
Microsoft 365 でドメインを設定するには、ドメインを所有し、ドメインの DNS レコードの一部を変更する必要があります。
  
> [!CAUTION]
> 一部のドメイン レジストラーまたは DNS ホスティング プロバイダーでは、Microsoft 365 で必要なすべての DNS レコードの作成が許可されていません。 必要なすべてのレコードをサポートしているホスティング プロバイダーの一覧を次に示します。 別のホスティング プロバイダーの使用を考えている場合は、 [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)してください。 
  
ドメインを (ドメイン レジストラーで) 登録した後、管理者として Microsoft 365 にサインインします。次に、電子メール アドレスやその他のサービスで使用できるようにドメインを設定します。
  
> [!NOTE]
> この記事の SharePoint Online パブリック Web サイト情報は、組織が 2015 年 3 月 9 日より前に Microsoft 365 を購入した場合にのみ適用されます。 

### <a name="domain-registrars-that-support-all-dns-records-required-for-microsoft-365"></a>Microsoft 365 に必要なすべての DNS レコードをサポートするドメイン レジストラー

- [Oray](https://oray.com/)

- [HiChina](https://www.hichina.com/)

- [east.net](http://www.east.net/)

- [BIZCN](https://www.bizcn.com/)

::: moniker-end

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 にドメインを追加する](../setup/add-domain.md) (記事)\
[ドメインの FAQ](../setup/domains-faq.yml) (記事)\
[現在のホスティング プロバイダーで Web サイトを維持するように DNS レコードを更新](../dns/update-dns-records-to-retain-current-hosting-provider.md) する (記事)
