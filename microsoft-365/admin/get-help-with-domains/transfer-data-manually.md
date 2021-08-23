---
title: 2 つのアカウント間でデータを手動で転送する
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: プランまたは会社名を変更した場合Microsoft 365複数のサブスクリプションを 1 に結合した場合に、2 つのアカウント間で手動でデータを転送する方法について説明します。
ms.openlocfilehash: e06136195481abcce66afa6ecc21d1c3c54415d7
ms.sourcegitcommit: 9469d16c6bbd29442a6787beaf7d84fb7699c5e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58400141"
---
# <a name="transfer-data-manually-between-two-accounts"></a>2 つのアカウント間でデータを手動で転送する

2 つの Microsoft 365 アカウント間でデータを転送するには、手動で複雑で時間のかかるプロセスです。 これは、自動化またはサポートされているプロセスではありません。 開始します。
  
> [!CAUTION]
> プロセス中に、電子メール、メール、Skype for Businessにホストされているパブリック web サイトが動作しないMicrosoft 365時間が発生します。 ユーザーには新しいユーザー名とパスワードが提供され、ユーザーは Outlook を再設定する必要があります。

**次のいずれかが当てはまる場合は、この記事の手順を使用して手動でデータを転送するしかありません。**
  
- 異なるサービス ファミリのプランに変更する必要がある場合。

- 会社名が変わったため、新しいサブスクリプションを作成し、異なる初期ドメイン名を使用するのでデータを移行する場合。

- 複数のサブスクリプションを 1 つの新しいサブスクリプションにまとめる必要がある場合。

> [!IMPORTANT]
> [サブスクリプション プランを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md) 必要があり、プラン切り替えウィザードを使用できる場合、またはプラン切り替えウィザードを使用できない場合でも同じサブスクリプション ファミリの新しいサブスクリプション プランに転送する必要がある場合は、手動でデータを転送する必要はないため、ダウンタイムは発生しません。

|**タスク**|**手順**|
|:-----|:-----|
|新たに希望するプランを購入します。  <br/> |サインアップするときは、初期ドメイン名 ( *yourcompany*  .onmicrosoft.com、  *yourcompany*  -public.sharepoint.com、  *yourcompany*  .sharepoint.com) で使用する会社名を指定します。既存のサブスクリプションとは異なる  *yourcompany*  名を使用する必要があります。  <br/> > [!NOTE]> 通常、サブスクリプションをキャンセルして、お客様の会社を使用する初期ドメイン名をシステムから解放するには、数か月以上かかる場合があります。 古い Microsoft 365 サブスクリプションからすべてのデータを保存し、そのサブスクリプションをキャンセルする場合でも、古い会社の値は新しいサブスクリプションですぐに使用できません。           |
|古いサブスクリプションからカスタム ドメインをMicrosoft 365します。  <br/> | [ドメインを削除する前に必要な手順](remove-a-domain.md) に従って、ユーザーのメール アドレスからドメイン名を削除し、メールの DNS レコードとカスタム ドメインの Lync を削除します。 パブリック Web サイトを Microsoft 365する場合は、それをポイントする CNAME レコードも削除する必要があります。  <br/> > [!IMPORTANT]>  このカスタム ドメインにメールをルーティングする MX レコードを削除すると、新しいアカウントにドメインを追加し、新しい MX レコードをセットアップして、ユーザーを設定するまで、メールは機能しなくなります。Lync の DNS レコードを削除すると、Lync は動作を停止します。また、パブリック Web サイトを指し示している CNAME レコードを削除した後は、Web サイトは使用できなくなります。           [ドメインを削除します](remove-a-domain.md) 。  <br/> |
|新しいサブスクリプションのカスタム ドメインをセットアップして、ユーザーを設定します。  <br/> | カスタム ドメインに必要な DNS レコードの作成など、新しいサブスクリプションをセットアップします。  <br/>  カスタム ドメインでのメール アドレスを指定して、ユーザーを作成します。  <br/> |
|古いサブスクリプションから新しいサブスクリプションにデータを転送します。  <br/> | 別のブラウザー ウィンドウで両方のアカウントにサインインします。  <br/>  ブラウザー アイコンを右クリックし、2 つのプライベート ブラウザー ウィンドウを開きます。 2 つのウィンドウで異なる資格情報を使用して、両方のアカウントにサインインできます。  <br/> [サブスクリプション間で管理の設定を転送する](#email) <br/> [チーム サイトの構造とデータを転送する](#transfer-team-site-structure-and-data) <br/> [サブスクリプション間でパブリック Web サイトを転送する](#transfer-a-public-website-between-subscriptions) <br/> [サブスクリプション間で管理の設定を転送する](#email) <br/> |
|Microsoft Support for microsoft Support for Microsoft 365 を呼び出して、完了したプランのサブスクリプションをキャンセルMicrosoft 365。  <br/> | 新しいサブスクリプションが動作していて、すべてのデータが転送されたことを確認します。  <br/>  [カスタマー サポートに問い合わせ](../../business-video/get-help-support.md) 、古いサブスクリプションをキャンセルします。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>サブスクリプション間で管理の設定を転送する

各アカウントで次のページに移動し、古いアカウントの設定に基づいて新しいアカウントを設定します。
  
データを Midsize Business または Microsoft 365 Microsoft 365に転送する場合Microsoft 365 Enterprise管理ページの構造が異なります。 ビデオを[見る: Microsoft 365 Enterprise](../index.yml)を紹介し、次の場所に移動して管理設定を確認します。
  
Midsize Business Microsoft 365 EnterpriseおよびMicrosoft 365の場合:
  
|**場所**|**目的**|
|:-----|:-----|
|**管理者** \>**Microsoft 365** \>**サービス設定** <br/> |メール、サイト、Lync、ユーザー ソフトウェア、パスワード、コミュニティ、権限管理、モバイルの設定の各タブを選択します。  <br/> |
|[ **管理者**] \> [ **Exchange**] <br/> | Exchange Online の設定  <br/> |
|[ **管理者**] \> [ **SharePoint**] <br/> | SharePoint Online の設定  <br/> |
|**管理者** \>**Skype for Business** <br/> |その他Skype for Business設定  <br/> |

小規模Microsoft 365向け
  
|**場所**|**目的**|
|:-----|:-----|
|[ **管理者**] \> [ **組織全体の設定を管理**] <br/> |管理の設定  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>サブスクリプション間でパブリック Web サイトを転送する

パブリック Web サイトをホストしている場合は、Microsoft 365保存し、新しいサブスクリプションに再作成する必要があります。
  
> [!NOTE]
> パブリック Web サイトが DNS ホスティング プロバイダーでホストされている場合は、変更する必要はありません。移行による影響はありません。
  
ドキュメント ライブラリやリスト コンテンツを SharePoint Online 環境からファイル共有やローカル コンピューターに保存するには、「[SharePoint Online コンテンツの手動移行に関する情報](/sharepoint/troubleshoot/migration-tool/content-manual-migration)」を参照してください。
  
> [!NOTE]
> パブリック サイト移行アプリでは、データを別のサブスクリプションに転送できません。
  
## <a name="transfer-team-site-structure-and-data"></a>チーム サイトの構造とデータを転送する

チーム サイトのデータを保存または転送するには複数の方法があります。
  
- 古いサイトをテンプレートとして保存し、新しいサイトにテンプレートをインポートできます。

- ドキュメントを転送するには、まず新しいサイトで階層を手動で再作成します。 その後は、両方の SharePoint チーム サイトを同時に開き、両方のドキュメント ライブラリをエクスプローラーで開いて、ドキュメントをコピーして貼り付けることができます。 「[ビデオ: [エクスプローラーで開く] を使用してライブラリ ファイルをコピーまたは移動する](../../business-video/store-files.md)」を参照してください。

- リスト データを転送するには、[リスト テンプレート](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)を保存し、保存したテンプレートを使用して新しいサイトにリストを再作成します。

- SharePoint Online 環境 (OneDrive for Business またはチーム サイト) からドキュメント ライブラリまたはリスト コンテンツをファイル共有またはローカル コンピューターに保存するには、「SharePoint Online コンテンツの手動移行[に関する情報」を](/sharepoint/troubleshoot/migration-tool/content-manual-migration)参照してください。

## <a name="transfer-users-data-between-subscriptions"></a>サブスクリプション間でユーザーのデータを転送する

### <a name="email"></a>電子メール:

新しいサブスクリプションを設定した後、[メール、連絡先、タスク、および予定表の情報を移動する](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc)ようにユーザーに依頼します。古いメールには、sue@contoso.onmicrosoft.com などの初期ユーザー名を使用してアクセスできます。
  
### <a name="onedrive-for-business-data"></a>OneDrive for Businessデータ:

ユーザーにコンテンツをコピー/同期[OneDrive for Businessして](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)、新しいサブスクリプションに追加し戻します。

### <a name="onenote"></a>OneNote 

[バックアップ] と[[OneNote](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us)から新しいサブスクリプションへのメモの[復元]](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us)をユーザーに求める。
