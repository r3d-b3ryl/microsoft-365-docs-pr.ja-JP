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
ms.localizationpriority: medium
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: セットアップ ウィザードを使用して、DNS ホストに DNS レコードMicrosoft 365追加Microsoft 365 管理センターにドメインを追加します。
ms.openlocfilehash: 7bb853e777ee0377ac0fb6ec6f7de453d4c4d4c7
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61373238"
---
# <a name="add-a-domain-to-microsoft-365"></a>Microsoft 365 にドメインを追加する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](domains-faq.yml)** を参照してください。 
  
## <a name="before-you-begin"></a>はじめに

ドメインを追加、変更、または **削除するには、** ビジネスプランまたはエンタープライズ プランの [グローバル管理者である必要があります](https://products.office.com/business/office)。 これらの変更はテナント全体に影響します。 *カスタマイズされた管理者* または *通常のユーザー* は、これらの変更を行う事ができません。

## <a name="watch-add-a-domain"></a>ウォッチ: ドメインの追加

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

会社によって、さまざまな目的で複数のドメイン名が必要になる場合があります。 たとえば、顧客が既にその会社名を使用していて、顧客とのコミュニケーションに失敗した場合、会社名に別のスペルを追加したい場合があります。

1. [設定] Microsoft 365 管理センター[セットアップ] を <a href="https://go.microsoft.com/fwlink/p/?linkid=2171997" target="_blank">**選択します**</a>。
1. [カスタム **ドメインのセットアップを取得する] で、[** ドメインの **管理**  >  **] を**  >  **選択します**。
1. 追加する新しいドメイン名を入力し、[**次へ**] を選択します。
1. ドメイン レジストラーにサインインし、[次へ] を **選択します**。
1. 新しいドメインのサービスを選択します。
1. [次 **の承認**  >  **]**  >  **を選択し**、[完了]**を選択します**。 新しいドメインが追加されました。

## <a name="add-a-domain"></a>ドメインの追加

以下の手順に従って、ドメインの追加、セットアップ、またはセットアップの続行を行います。 

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> から管理センターにアクセスします。

::: moniker-end
    
2. [**設定**]  >  [**ドメイン**] ページの順に移動します。 

3. [**ドメインの追加**] を選択します。
    
4. 追加するドメインの名前を入力し、**[次へ]** を選択します。
    
5. ドメインの所有を確認する方法を選択します。
    
    1. ドメイン レジストラーが[ドメイン接続](#domain-connect-registrars-integrating-with-microsoft-365)を使用している場合、Microsoft は、レジストラーにサインインして Microsoft 365への接続を確認することにより、[レコードを自動的に設定します](../get-help-with-domains/domain-connect.md)。 管理センターに戻り、Microsoft がドメインを自動的に確認します。
    2. TXT レコードを使用し、ドメインを検証できます。 これを選択し、**[次へ]** を選択すると、この DNS レコードをレジストラーの Web サイトに追加する方法が表示されます。 レコードを追加すると、検証に最大 30 分かかることがあります。 
    3. ドメインの Web サイトにテキスト ファイルを追加できます。 セットアップ ウィザードから .txt ファイルを選択してダウンロードし、そのファイルを Web サイトの最上位フォルダーにアップロードします。 ファイルへのサーバー相対パスは、次のようになります: `http://mydomain.com/ms39978200.txt`。 Web サイトでファイルを検索して、ドメインを所有していることを確認します。
    
6. Microsoft でドメインを使用するために必要な DNS 変更の方法を選択します。
    
    1. レジストラーが [ドメイン接続](#domain-connect-registrars-integrating-with-microsoft-365)をサポートしている場合は、**[DNS レコードの追加]** を選択します。Microsoft は、レジストラーにサインインしてMicrosoft 365 への接続を確認することにより、[レコードを自動的に設定します](../get-help-with-domains/domain-connect.md)。
    2. 特定の Microsoft 365 サービスのみをドメインに追加する場合、またはここではこの手順をスキップして後で行う場合、**[DNS レコードを自分で追加する]** を選択します。 **次のように、操作内容を正確に把握している場合に、このオプションを選択します。**

7. *[DNS レコードを自分で追加する]* を選択した場合、**[次へ]** を選択します。そして、ドメインを設定するために、レジストラー Web サイトに追加する必要があるすべてのレコードが含まれるページが表示されます。 

    ポータルでレジストラーが認識されない場合、[一般的な方法に従うことができます](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。
    
    ドメインの DNS ホスティング プロバイダーまたはドメイン レジストラーがわからない場合は、「[ドメイン レジストラーまたは DNS ホスティング プロバイダーを探す](../get-help-with-domains/find-your-domain-registrar.md)」を参照してください。
    
    しばらく待つ場合は、すべてのサービスの選択を解除して **[続行]** をクリックするか、前のドメイン接続手順で **[その他のオプション]** を選択して **[今はスキップ]** を選択します。
    
8. **[完了]** を選択します。これで完了です!

## <a name="add-or-edit-custom-dns-records"></a>カスタムの DNS レコードを追加または編集する

以下の手順に従って、Web サイトまたはサード パーティ サービスのカスタム レコードを追加します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>で Microsoft 365 管理センターにサインインします。

2. [**設定**]   >  [**ドメイン**] ページの順に移動します。

3. [**ドメイン**] ページで、ドメインを選びます。 
    
4. **[DNS 設定]** で、**[カスタム レコード]** を選択します。 次に、**[新しいカスタム レコード]** を選択します。

5. 追加する DNS レコードの種類を選択し、新しいレコードの情報を入力します。
    
6. **[保存]** を選択します。

## <a name="registrars-with-domain-connect"></a>ドメイン接続を使用するレジストラ

[ドメイン接続](https://www.domainconnect.org/) 対応のレジストラを使用すると、3 ステップの手順を使って、数分でドメインを Microsoft 365 に追加できます。 
  
ウィザードでは、ドメインを所有していることを確認してから、ドメインのレコードを自動的に設定するため、Microsoft 365 にメールが送信されます。Teams などの他の Microsoft 365 サービスはドメインを操作します。
  
> [!NOTE]
> セットアップ ウィザードを開始する前に、ブラウザーのポップアップ ブロック機能が無効になっていることを確認してください。
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365 と統合するドメイン接続レジストラ

- [1&amp;1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [Go Daddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer または WildWestDomains (SecureServer DNS ホスティングを使用する GoDaddy リセラー)
    - 例:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>メールと Web サイトはどうなりますか?

セットアップを終了すると、ユーザーのドメインの MX レコードが Microsoft 365 を指定されるように更新され、そのドメイン宛てのすべてのメールが Microsoft 365 に送信されるようになります。 ユーザーのドメインにメールを持つすべてのユーザーが Microsoft 365 に追加され、メールボックスが設定されていることを確認してください。
  
ビジネスで使用している Web サイトがある場合は、そのままの場所で稼働し続けます。 ドメイン接続 のセットアップ手順は、自分の Web サイトには影響しません。

## <a name="related-content"></a>関連コンテンツ

[ドメインに関する FAQ](domains-faq.yml) (記事) [ドメインとは](../get-help-with-domains/what-is-a-domain.md) (記事)[ドメイン名を購入する](../get-help-with-domains/buy-a-domain-name.md)(Microsoft 365)\
[DNS レコードを追加して](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)ドメインに接続する ([記事)](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md)ネームサーバーを変更して、Microsoft 365レジストラーと一緒に設定する (記事)