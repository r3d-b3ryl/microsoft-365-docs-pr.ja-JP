---
title: 2つのアカウント間でデータを手動で転送する
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
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: プランまたは会社名を変更したとき、または複数のサブスクリプションを1つに結合したときに、2つの Microsoft 365 アカウント間でデータを手動で転送する方法について説明します。
ms.openlocfilehash: 1eaaf48f445eb54ebf91b96924c39e9062eea4fb
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053742"
---
# <a name="transfer-data-manually-between-two-accounts"></a>2つのアカウント間でデータを手動で転送する

Sleeves をロールアップし、予定表の時間をブロックするように準備します。2つの Microsoft 365 アカウント間でデータを転送することは、手動で複雑で時間のかかるプロセスです。 これは、自動化またはサポートされているプロセスではありません。 開始します。
  
> [!CAUTION]
> 電子メール、Skype for Business、および Microsoft 365 でホストされているパブリック web サイトが機能しないプロセスの間に、ダウンタイムが発生します。 ユーザーには新しいユーザー名とパスワードが提供され、ユーザーは Outlook を再設定する必要があります。

**次のいずれかが当てはまる場合は、この記事の手順を使用して手動でデータを転送するしかありません。**
  
- 異なるサービス ファミリのプランに変更する必要がある場合。

- 会社名が変わったため、新しいサブスクリプションを作成し、異なる初期ドメイン名を使用するのでデータを移行する場合。

- 複数のサブスクリプションを 1 つの新しいサブスクリプションにまとめる必要がある場合。

> [!IMPORTANT]
> [サブスクリプション プランを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md) 必要があり、プラン切り替えウィザードを使用できる場合、またはプラン切り替えウィザードを使用できない場合でも同じサブスクリプション ファミリの新しいサブスクリプション プランに転送する必要がある場合は、手動でデータを転送する必要はないため、ダウンタイムは発生しません。

|**タスク**|**手順**|
|:-----|:-----|
|新たに希望するプランを購入します。  <br/> |サインアップするときは、初期ドメイン名 ( *yourcompany*  .onmicrosoft.com、  *yourcompany*  -public.sharepoint.com、  *yourcompany*  .sharepoint.com) で使用する会社名を指定します。既存のサブスクリプションとは異なる  *yourcompany*  名を使用する必要があります。  <br/> > [!NOTE]>  通常、  *yourcompany*  を使用する初期ドメイン名をシステムから解放するには、サブスクリプションを取り消してから数か月以上かかります。 古い Microsoft 365 サブスクリプションからすべてのデータを保存することを計画している場合でも、そのサブスクリプションを取り消すと、古い*会社*の値を新しいサブスクリプションですぐに使用することはできません。           |
|古い Microsoft 365 サブスクリプションからカスタムドメインを削除します。  <br/> | [ドメインを削除する前に必要な手順](remove-a-domain.md) に従って、ユーザーのメール アドレスからドメイン名を削除し、メールの DNS レコードとカスタム ドメインの Lync を削除します。 Microsoft 365 でパブリック web サイトをホストしている場合は、それを指す CNAME レコードも削除する必要があります。  <br/> > [!IMPORTANT]>  このカスタム ドメインにメールをルーティングする MX レコードを削除すると、新しいアカウントにドメインを追加し、新しい MX レコードをセットアップして、ユーザーを設定するまで、メールは機能しなくなります。Lync の DNS レコードを削除すると、Lync は動作を停止します。また、パブリック Web サイトを指し示している CNAME レコードを削除した後は、Web サイトは使用できなくなります。           [ドメインを削除します](remove-a-domain.md) 。  <br/> |
|新しいサブスクリプションのカスタム ドメインをセットアップして、ユーザーを設定します。  <br/> | カスタム ドメインに必要な DNS レコードの作成など、新しいサブスクリプションをセットアップします。  <br/>  カスタム ドメインでのメール アドレスを指定して、ユーザーを作成します。  <br/> |
|古いサブスクリプションから新しいサブスクリプションにデータを転送します。  <br/> | 別のブラウザー ウィンドウで両方のアカウントにサインインします。  <br/>  Internet Explorer のアイコンを右クリックし、InPrivate ブラウザー ウィンドウを 2 つ開きます。2 つのウィンドウで異なる資格情報を使用して、両方のアカウントにサインインできます。  <br/> [サブスクリプション間で管理の設定を転送する](#email) <br/> [チーム サイトの構造とデータを転送する](#transfer-team-site-structure-and-data) <br/> [サブスクリプション間でパブリック Web サイトを転送する](#transfer-a-public-website-between-subscriptions) <br/> [サブスクリプション間で管理の設定を転送する](#email) <br/> |
|Microsoft 365 の Microsoft サポートに連絡して、実行しているプランのサブスクリプションをキャンセルします。  <br/> | 新しいサブスクリプションが動作していて、すべてのデータが転送されたことを確認します。  <br/>  [カスタマーサポートに連絡](../contact-support-for-business-products.md)して、古いサブスクリプションを解約してください。  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>サブスクリプション間で管理の設定を転送する

各アカウントで次のページに移動し、古いアカウントの設定に基づいて新しいアカウントを設定します。
  
Microsoft 365 から Microsoft 365 中規模企業または Microsoft 365 Enterprise にデータを転送する場合、管理ページの構造は異なります。 [「Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)」を参照し、次の場所に移動して、管理設定を確認してください。
  
Microsoft 365 Enterprise および Microsoft 365 中規模企業の場合:
  
|**場所**|**目的**|
|:-----|:-----|
|**Admin** \> **Microsoft 365** \> **サービスの設定** <br/> |メール、サイト、Lync、ユーザーソフトウェア、パスワード、コミュニティ、rights management、およびモバイルの設定については、各タブを選択します。  <br/> |
|[ **管理者**] \> [ **Exchange**] <br/> | Exchange Online の設定  <br/> |
|[ **管理者**] \> [ **SharePoint**] <br/> | SharePoint Online の設定  <br/> |
|**Admin** \> **Skype for business の**管理 <br/> |その他の Skype for Business の設定  <br/> |

Microsoft 365 Small Business の場合
  
|**場所**|**目的**|
|:-----|:-----|
|[ **管理者**] \> [ **組織全体の設定を管理**] <br/> |管理の設定  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>サブスクリプション間でパブリック Web サイトを転送する

Microsoft 365 でホストされているパブリック web サイトがある場合は、それを保存して、新しいサブスクリプションで再作成する必要があります。
  
> [!NOTE]
> パブリック Web サイトが DNS ホスティング プロバイダーでホストされている場合は、変更する必要はありません。移行による影響はありません。
  
ドキュメント ライブラリやリスト コンテンツを SharePoint Online 環境からファイル共有やローカル コンピューターに保存するには、「[SharePoint Online コンテンツの手動移行に関する情報](https://go.microsoft.com/fwlink/p/?LinkId=402910)」を参照してください。
  
> [!NOTE]
> パブリック サイト移行アプリでは、データを別のサブスクリプションに転送できません。
  
## <a name="transfer-team-site-structure-and-data"></a>チーム サイトの構造とデータを転送する

チーム サイトのデータを保存または転送するには複数の方法があります。
  
- 古いサイトをテンプレートとして保存し、新しいサイトにテンプレートをインポートできます。

- ドキュメントを転送するには、最初に新しいサイトで階層を手動で再作成します。 その後は、両方の SharePoint チーム サイトを同時に開き、両方のドキュメント ライブラリをエクスプローラーで開いて、ドキュメントをコピーして貼り付けることができます。 「[ビデオ: [エクスプローラーで開く] を使用してライブラリ ファイルをコピーまたは移動する](https://support.office.com/article/where-to-store-files-c7c20284-bc94-47f4-9728-d28e9daf0790)」を参照してください。

- リスト データを転送するには、[リスト テンプレート](https://support.microsoft.com/en-us/office/manage-list-templates-c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)を保存し、保存したテンプレートを使用して新しいサイトにリストを再作成します。

- SharePoint Online 環境 (OneDrive for Business またはチームサイト) からファイル共有またはローカルコンピューターにドキュメントライブラリまたはリストのコンテンツを保存するには、「 [Sharepoint online コンテンツの手動での移行に関する情報](https://support.microsoft.com/kb/2783484)」を参照してください。

## <a name="transfer-users-data-between-subscriptions"></a>サブスクリプション間でユーザーのデータを転送する

### <a name="email"></a>電子メール:

新しいサブスクリプションを設定した後、[メール、連絡先、タスク、および予定表の情報を移動する](https://support.office.com/article/0996ece3-57c6-49bc-977b-0d1892e2aacc.aspx)ようにユーザーに依頼します。古いメールには、sue@contoso.onmicrosoft.com などの初期ユーザー名を使用してアクセスできます。
  
### <a name="onedrive-for-business-data"></a>OneDrive For Business データ:

ユーザーに[OneDrive For business のコンテンツを自分のコンピューターに](https://support.office.com/article/59b1de2b-519e-4d3a-8f45-51647cf291cd.aspx)コピー/同期させ、新しいサブスクリプションに追加してもらいます。
