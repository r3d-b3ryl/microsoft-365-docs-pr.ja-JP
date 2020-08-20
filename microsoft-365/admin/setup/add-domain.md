---
title: Microsoft 365 にドメインを追加する
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Microsoft 365 管理センターで Microsoft 365 にドメインを追加するには、DNS ホストで DNS レコードを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814434"
---
# <a name="add-a-domain-to-microsoft-365"></a>Microsoft 365 にドメインを追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

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
    
2. [**設定**]  >  [**ドメイン**] ページの順に移動します。 

3. [**ドメインの追加**] を選択します。
    
4. 追加するドメインの名前を入力し、**[次へ]** を選択します。
    
5. ドメインの所有を確認する方法を選択します。
    
    1. ドメインが GoDaddy または 1 &amp; 1 に登録されている場合は、[**次へ Sign in**  >  **Next]** を選び、Microsoft[がレコードを自動的に設定します](../get-help-with-domains/domain-connect.md)。
    
    2. ドメインに登録している連絡先に、検証コードを含むメールを送信できます。 レコードのメールに見覚えがない、またはメールにアクセスできない場合、3 番目のオプションを利用できます。
    
    3. TXT レコードを使用し、ドメインを検証できます。 これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。 レコードを追加すると、検証に最大 30 分かかることがあります。 
    
6. Office でドメインを使用するために必要な DNS 変更の方法を選択します。
    
    1. DNS を Office に自動構成させる場合、**[DNS レコードを追加してもらう]** を選択します。 
    
  
    2. 自分 **で DNS レコードを自分で追加します。** その場合、特定の Microsoft 365 サービスのみをドメインに接続する場合、またはここではスキップして後で行います。 **次のように、操作内容を正確に把握している場合に、このオプションを選択します。**
    
7. *DNS レコードを自分で追加する*を選択した場合、**[次へ]** を選択します。そして、ドメインを設定するために、レジストラー Web サイトに追加する必要があるすべてのレコードが含まれるページが表示されます。 
    
  
  
    ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
    [ホスト固有の命令](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。 
    
    ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
    
    後で行う場合、下にスクロールして **[この手順をスキップ]** を選択します。
    
8. **[完了]** を選択します。これで完了です! 

## <a name="add-or-edit-custom-dns-records"></a>カスタムの DNS レコードを追加または編集する

Web サイトまたはサード パーティのサービスのカスタム レコードを追加するには、以下の手順に従います。

1. Microsoft 管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. [**設定**]   >  [**ドメイン**] ページの順に移動します。

3. [ **ドメイン**] ページで、ドメインを選びます。 
    
4. [DNS **設定] で**、[カスタム レコード **] を選択します**。次に新しい **カスタム レコードを選択します**。

5. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。
    
6. **[保存]** を選択します。

## <a name="registrars-with-domain-connect"></a>Domain Connect を使用したレジストラー

[ドメイン接続](https://www.domainconnect.org/) が有効になっているレジストラーでは、3 段階のプロセスで Microsoft 365 にドメインを追加できますが、少し時間がかかります。 
  
ウィザードでは、ドメインを所有していることを確認したうし、ドメインのレコードが自動的にセットアップされるので、Microsoft 365 や Teams などの他の Microsoft 365 サービスが自分のドメインで機能するようにメールが送信されます。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 との統合ドメイン接続レジストラー

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)
    - [MadDog Domains](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>電子メールと Web サイトはどうなりうですか?

セットアップを終了すると、ユーザーのドメインの MX レコードが Microsoft 365 を指定するように更新され、そのドメインのすべてのメールが Microsoft 365 に送信されるされるになります。 ユーザーのドメインにメールを持つすべてのユーザーが Microsoft 365 に追加され、メールボックスが設定されている必要があります。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続のセットアップ手順は、Web サイトには影響を与えない。

## <a name="related-articles"></a>関連記事

[ドメイン FAQ](domains-faq.md)

[ドメインとは](../get-help-with-domains/what-is-a-domain.md)

[Microsoft 365 でドメイン名を購入する](../get-help-with-domains/buy-a-domain-name.md)

[ドメインを設定する (ホストに固有の手順)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
