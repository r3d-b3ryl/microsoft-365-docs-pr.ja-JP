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
description: Dns レコードを DNS ホストに追加して、365 Microsoft 365 の microsoft にドメインを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 09a66b9ac4f97a076d71dd7f259678181378ae48
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295024"
---
# <a name="add-a-domain-to-microsoft-365"></a>Microsoft 365 にドメインを追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

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
    
    1. ドメインレジストラーが [ドメイン接続](#domain-connect-registrars-integrating-with-microsoft-365)を使用している場合、microsoft はレジストラーにサインインして microsoft 365 への接続を確認することによって、 [レコードを自動的に](../get-help-with-domains/domain-connect.md) セットアップします。 管理センターに戻り、Microsoft がドメインを自動的に検証するようになります。
    2. TXT レコードを使用し、ドメインを検証できます。 これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。 レコードを追加すると、検証に最大 30 分かかることがあります。 
    3. ドメインの web サイトにテキストファイルを追加することができます。 セットアップウィザードから .txt ファイルを選択してダウンロードし、web サイトの最上位レベルのフォルダーにファイルをアップロードします。 ファイルへのパスは、次のようになり `http://mydomain.com/ms39978200.txt` ます。 Web サイトでファイルを検索して、ドメインを所有していることを確認します。
    
6. Microsoft がドメインを使用するために必要な DNS 変更を行う方法を選択します。
    
    1. レジストラーが[ドメイン接続](#domain-connect-registrars-integrating-with-microsoft-365)をサポートしている場合は **、[DNS レコードを追加**する] を選択し、microsoft はレジストラーにサインインして microsoft 365 への接続を確認して、[レコードを自動的に](../get-help-with-domains/domain-connect.md)セットアップします。
    2. 特定の Microsoft 365 サービスのみをドメインに接続する場合、またはこれを今後スキップする場合は **、[自分で DNS レコードを追加** する] を選択します。 **次のように、操作内容を正確に把握している場合に、このオプションを選択します。**

7. *DNS レコードを自分で追加*することを選択した場合は、[**次へ**] を選択すると、レジストラーの web サイトに追加する必要があるすべてのレコードがあるページが表示され、ドメインをセットアップすることができます。 

    ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
    [ホスト固有の命令](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。 
    
    ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
    
    後で待機する場合は、すべてのサービスの選択を解除して [ **続行**] をクリックするか、または [前のドメイン接続] ステップで [ **その他のオプション** ] を選択し、[ **これはスキップ**します] を選択します。
    
8. **[完了]** を選択します。これで完了です!

## <a name="add-or-edit-custom-dns-records"></a>カスタムの DNS レコードを追加または編集する

Web サイトまたはサードパーティサービスのカスタムレコードを追加するには、以下の手順を実行します。

1. Microsoft 管理センターにサインイン <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. [**設定**]   >  [**ドメイン**] ページの順に移動します。

3. [ **ドメイン**] ページで、ドメインを選びます。 
    
4. [ **DNS 設定**] で、[ **カスタムレコード**] を選択します。次に、[ **新しいカスタムレコード**] を選択します。

5. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。
    
6. **[保存]** を選択します。

## <a name="registrars-with-domain-connect"></a>レジストラーとドメイン接続

[ドメイン接続](https://www.domainconnect.org/) が有効な登録機関は、数分かかる3つのステップのプロセスで、ドメインを Microsoft 365 に追加することができます。 
  
このウィザードでは、ドメインを所有していることを確認し、ドメインのレコードを自動的に設定することを確認します。そのため、Microsoft 365 およびその他の Microsoft 365 サービス (Teams など) が自分のドメインで作業します。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合するドメイン接続レジストラー

- [1 &amp; IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy 販売店)
    - 例:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [Domainall 現在](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>電子メールと web サイトはどうなりますか?

セットアップが完了すると、ドメインの MX レコードが更新され、Microsoft 365 をポイントするようになり、ドメインのすべての電子メールが Microsoft 365 に送られ始めます。 自分のドメインで電子メールを取得するすべてのユーザーについて、Microsoft 365 でユーザーを追加し、メールボックスを設定していることを確認してください。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続のセットアップ手順は、web サイトには影響しません。

## <a name="related-articles"></a>関連記事

[ドメイン FAQ](domains-faq.md)

[ドメインとは](../get-help-with-domains/what-is-a-domain.md)

[Microsoft 365 でドメイン名を購入する](../get-help-with-domains/buy-a-domain-name.md)

[ドメインを設定する (ホストに固有の手順)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
