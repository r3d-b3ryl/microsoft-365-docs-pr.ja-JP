---
title: Office 365 にドメインを追加する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Microsoft 365 管理センターで Office 365 にドメインを追加するには、 DNS ホストで DNS レコードを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 8e08233ffe33ac2b5d41ad164af80468de52983d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631817"
---
# <a name="add-a-domain-to-office-365"></a>Office 365 にドメインを追加する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.md)** を参照してください。 
  
 *追加、変更またはドメインを削除するには、[ビジネスまたはエンタープライズ プラン](https://products.office.com/business/office)の**グローバル管理者**である**必要**があります。これらの変更は、テナント全体、*カスタマイズ管理者*または*正規ユーザー*に影響を与え、変更を加えることはできません。*  

 以下の手順に従って、ドメインの追加、セットアップ、またはセットアップの続行を行います。 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。

::: moniker-end
::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。

::: moniker-end
    
2. [**セットアップ** > **ドメイン**] ページに移動します。 

3. [**ドメインの追加**] を選択します。
    
4. 追加するドメインの名前を入力し、**[次へ]** を選択します。
    
5. ドメインの所有を確認する方法を選択します。
    
    1. ドメインが GoDaddy または 1&amp;1 で登録されている場合は、[**次へ**] を選択**Sign in** > すると、Microsoft に[よってレコードが自動的に設定され](../get-help-with-domains/domain-connect.md)ます。
    
    2. ドメインに登録している連絡先に、検証コードを含むメールを送信できます。 レコードのメールに見覚えがない、またはメールにアクセスできない場合、3 番目のオプションを利用できます。
    
    3. TXT レコードを使用し、ドメインを検証できます。 これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。 レコードを追加すると、検証に最大 30 分かかることがあります。 
    
6. Office でドメインを使用するために必要な DNS 変更の方法を選択します。
    
    1. DNS を Office に自動構成させる場合、**[DNS レコードを追加してもらう]** を選択します。 
    
  
    2. 特定の Office 365 サービスのみをドメインに追加する場合、またはここではこの手順をスキップして後で行う場合、**[DNS レコードを自分で追加する]** を選択します。 **次のように、操作内容を正確に把握している場合に、このオプションを選択します。**
    
7. *DNS レコードを自分で追加する*を選択した場合、**[次へ]** を選択します。そして、ドメインを設定するために、レジストラー Web サイトに追加する必要があるすべてのレコードが含まれるページが表示されます。 
    
  
  
    ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
    [ホスト固有の命令](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。 
    
    ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
    
    後で行う場合、下にスクロールして **[この手順をスキップ]** を選択します。
    
8. **[完了]** を選択します。これで完了です! 

## <a name="related-articles"></a>関連記事

[ドメイン FAQ](domains-faq.md)

[ドメインとは](../get-help-with-domains/what-is-a-domain.md)

[Office 365 でドメイン名を購入する](../get-help-with-domains/buy-a-domain-name.md)

[ドメインを設定する (ホスト固有の手順)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[ドメインに関するヘルプを取得する](../get-help-with-domains/get-help-with-domains.md)
