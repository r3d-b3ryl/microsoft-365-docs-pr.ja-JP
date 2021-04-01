---
title: Microsoft 365 にドメインを追加する
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
description: DNS ホストに DNS レコードを追加して、Microsoft 365 管理センターの Microsoft 365 にドメインを追加します。 これらの手順を案内するウィザードがあります。
ms.openlocfilehash: 747de5f61dc9fce53f82f52b65f701572a56f8d4
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470883"
---
# <a name="add-a-domain-to-microsoft-365"></a>Microsoft 365 にドメインを追加する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.yml)** を参照してください。 
  
 *追加、変更またはドメインを削除するには、[ビジネスまたはエンタープライズ プラン](https://products.office.com/business/office)の **グローバル管理者** である **必要** があります。これらの変更は、テナント全体、*カスタマイズ管理者* または *正規ユーザー* に影響を与え、変更を加えることはできません。*  

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
    
    1. ドメイン レジストラーが [ドメイン](#domain-connect-registrars-integrating-with-microsoft-365)接続を使用している場合 [、Microsoft](../get-help-with-domains/domain-connect.md) はレジストラーにサインインし、Microsoft 365 への接続を確認することでレコードを自動的にセットアップします。 管理センターに戻り、Microsoft がドメインを自動的に確認します。
    2. TXT レコードを使用し、ドメインを検証できます。 これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。 レコードを追加すると、検証に最大 30 分かかることがあります。 
    3. ドメインの Web サイトにテキスト ファイルを追加できます。 セットアップ ウィザードから .txt ファイルを選択してダウンロードし、そのファイルを Web サイトのトップ レベル フォルダーにアップロードします。 ファイルへのパスは、次のように表示されます `http://mydomain.com/ms39978200.txt` 。 Web サイトでファイルを見つけて、ドメインを所有しているのを確認します。
    
6. Microsoft がドメインを使用するために必要な DNS 変更を行う方法を選択します。
    
    1. レジスト **ラーが** ドメイン接続をサポートしている場合は、[DNS [](#domain-connect-registrars-integrating-with-microsoft-365)レコードを追加する] を選択し [、レジストラー](../get-help-with-domains/domain-connect.md)にサインインして Microsoft 365 への接続を確認することでレコードを自動的にセットアップします。
    2. 特定 **の** Microsoft 365 サービスのみをドメインに接続する場合、または今のところこれをスキップして後で行う場合は、[自分で DNS レコードを追加する] を選択します。 **次のように、操作内容を正確に把握している場合に、このオプションを選択します。**

7. DNS レコードを自分で追加することを選択した場合は、[次へ] を選択すると、ドメインを設定するためにレジストラー Web サイトに追加する必要があるすべてのレコードを含むページが表示されます。 

    ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
    [ホスト固有の命令](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)の一覧からお使いのホストを見つけ、手順に従って必要なすべてのレコードを追加します。 
    
    ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
    
    後で待機する場合は、すべてのサービスの選択を解除して [続行] をクリックするか、前のドメイン接続手順で [その他のオプション] を選択し、[今のところスキップする] を **選択します**。
    
8. **[完了]** を選択します。これで完了です!

## <a name="add-or-edit-custom-dns-records"></a>カスタムの DNS レコードを追加または編集する

Web サイトまたはサードパーティ サービスのカスタム レコードを追加するには、以下の手順に従います。

1. で Microsoft 管理センターにサインインします <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。

2. [**設定**]   >  [**ドメイン**] ページの順に移動します。

3. [ **ドメイン**] ページで、ドメインを選びます。 
    
4. **[DNS 設定] で**、[カスタム レコード **] を選択します**。次に、[**新しいカスタム レコード] を選択します**。

5. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。
    
6. **[保存]** を選択します。

## <a name="registrars-with-domain-connect"></a>ドメイン接続を使用するレジストラー

[ドメイン接続](https://www.domainconnect.org/) が有効なレジストラーを使用すると、数分かかる 3 つの手順で Microsoft 365 にドメインを追加できます。 
  
ウィザードでは、ドメインを所有し、ドメインのレコードを自動的に設定するだけなので、Microsoft 365 や Teams などの他の Microsoft 365 サービスにメールが届きます。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合されたドメイン接続レジストラー

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)
    - 例:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>メールと Web サイトは何が起こりますか?

セットアップが完了すると、ドメインの MX レコードが Microsoft 365 をポイントして更新され、ドメインのすべてのメールが Microsoft 365 に送信されます。 ドメインでメールを受け取るすべてのユーザーに対して、ユーザーを追加し、Microsoft 365 でメールボックスを設定してください。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続のセットアップ手順は、Web サイトには影響を与えかねない。

## <a name="related-articles"></a>関連記事

[ドメイン FAQ](domains-faq.yml)

[ドメインとは](../get-help-with-domains/what-is-a-domain.md)

[Microsoft 365 でドメイン名を購入する](../get-help-with-domains/buy-a-domain-name.md)

[ドメインを設定する (ホストに固有の手順)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)