---
title: ゲストと共同でドキュメントの作業をする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: この記事では、SharePoint および OneDrive のドキュメントでゲストを使用して共同作業を行う方法について説明します。
ms.openlocfilehash: 022811be642a79c07c632cefcc67a27f19e3af4f
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422607"
---
# <a name="collaborate-with-guests-on-a-document"></a>ゲストと共同でドキュメントの作業をする

SharePoint または OneDrive のドキュメントで組織外のユーザーと共同作業を行う必要がある場合は、ドキュメントへの共有リンクを送信することができます。 この記事では、組織のニーズに合わせて SharePoint と OneDrive の共有リンクを設定するために必要な、Microsoft 365 の構成手順について説明します。

## <a name="video-demonstration"></a>ビデオ デモンストレーション

このビデオでは、このドキュメントで説明されている構成手順を示します。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Azure の組織上の関係の設定

Microsoft 365 での共有は、 [Azure Active Directory の組織上の関係の設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)によって最上位レベルで管理されます。 Azure AD でゲスト共有が無効または制限されている場合、この設定は、Microsoft 365 で構成した共有設定よりも優先されます。

組織上の関係の設定を確認して、ゲストとの共有がブロックされないようにしてください。

![Azure Active Directory における組織の関係の設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

組織上の関係の設定を設定するには

外部グループ作業設定を設定するには

1. Azure Active Directory にログイン [https://aad.portal.azure.com](https://aad.portal.azure.com) します。
2. 左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。
3. [ **外部 id**] をクリックします。
4. [ **作業の開始** ] 画面の左側のナビゲーションウィンドウで、[ **外部グループ作業の設定**] をクリックします。
5. **管理者とゲスト招待元役割のユーザーが招待できる**ことと、**メンバーが招待**できることを確認します。どちらも **[はい]** に設定されています。
6. 変更を加えた場合は、[**保存**] をクリックします。

[ **共同作業の制限** ] セクションの設定に注意してください。 共同作業を行うゲストのドメインがブロックされていないことを確認します。

複数の組織のゲストを使用している場合は、ディレクトリデータへのアクセスを制限することをお客様に許可します。 これにより、他のユーザーがディレクトリ内のゲストであることを確認できなくなります。 これを行うには、[ **ゲストユーザーのアクセス制限**] で、[ゲストユーザー **がアクセスを制限しているのは、ディレクトリオブジェクトのプロパティとメンバーシップ] 設定** または **guest ユーザーアクセスが、自分のディレクトリオブジェクトのプロパティとメンバーシップに制限され**ています。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織レベルでの共有設定

組織外のユーザーが SharePoint または OneDrive のドキュメントにアクセスできるようにするには、SharePoint および OneDrive の組織レベルでの共有設定で、組織外のユーザーとの共有が許可されている必要があります。

SharePoint の組織レベルの設定により、個々の SharePoint サイトで使用できる設定が決定されます。 サイトの設定は、組織レベルの設定よりも制限することはできません。 OneDrive の組織レベルの設定により、ユーザーの OneDrive ライブラリで利用できる共有のレベルが決定されます。

SharePoint と OneDrive の場合は、認証されていないファイルとフォルダーの共有を許可する場合は、[ **すべて**] を選択します。 組織外のユーザーが認証を必要とするようにするには、[ **新規および既存のゲスト**] を選択します。 [*全員*] リンクは最も簡単に共有する方法です。組織外のユーザーは、認証なしでリンクを開くことができ、他のユーザーに渡すことができます。

SharePoint の場合は、組織内のすべてのサイトで必要とされる最も寛容な設定を選択します。

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 組織レベルの共有設定を設定するには

1. Microsoft 365 管理センターの左側のナビゲーションウィンドウで、[ **管理センター**] の下の [ **SharePoint**] をクリックします。
2. SharePoint 管理センターの左側のナビゲーションウィンドウで、[ **ポリシー**] の下にある [ **共有**] をクリックします。
3. SharePoint または OneDrive の外部共有が [すべての **ユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。 (OneDrive の設定は、SharePoint の設定よりも制限がないことに注意してください)。
4. 変更を加えた場合は、[**保存**] をクリックします。

## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint 組織レベルの既定のリンク設定

既定のファイルおよびフォルダーのリンク設定は、ファイルまたはフォルダーを共有するときに既定でユーザーに表示されるリンクオプションを決定します。 必要に応じて、共有する前に、リンクの種類を他のオプションのいずれかに変更できます。

この設定は、組織内の SharePoint サイトや OneDrive に影響を与えることに注意してください。

ユーザーがファイルやフォルダーを共有するときに既定で選択される、次のいずれかの種類のリンクを選択します。

- **リンクを持つすべてのユーザー** -認証されていないファイルとフォルダーの共有が頻繁に行われるようにする場合は、このオプションを選択します。 *すべて*のリンクを許可し、偶発的な認証されていない共有について懸念している場合は、他のオプションのいずれかを既定値として検討します。 このリンクの種類は、 **すべて** の共有を有効にした場合にのみ使用できます。
- [**組織内のユーザーのみ**]-ほとんどのファイルとフォルダーの共有が組織内のユーザーと想定される場合は、このオプションを選択します。
- **特定のユーザー** -多数のファイルとフォルダーをゲストで共有することが予想される場合は、このオプションを検討してください。 この種類のリンクはゲストと連動しており、認証を必要とします。
 
![SharePoint における組織レベルのファイルとフォルダー設定のスクリーンショット](../media/sharepoint-organization-files-folders-sharing-settings.png)


SharePoint と OneDrive の組織レベルの既定のリンク設定を設定するには

1. SharePoint 管理センターの [共有] ページに移動します。
2. [ **ファイルとフォルダーのリンク**] で、使用する既定の共有リンクを選択します。
3. 変更を加えた場合は、[**保存**] をクリックします。

共有リンクのアクセス許可を設定するには、[ **共有リンク] で既定で選択されているアクセス許可を選択します。**

1. 認証されていないユーザーがファイルやフォルダーを変更できないようにする場合は、[ **表示** ] を選択します。
2. 認証されていないユーザーがファイルやフォルダーを変更できるようにする場合は、[ **編集** ] を選択します。

上記の2つの事前ミッションオプションは、ゲスト/外部ユーザーに対してだけでなく、内部ユーザーに対しても適用できます。 選択する権限オプションは、自己決定によって決定されます。

他のユーザーとの共有を許可するリンクにアクセス許可を設定するには

1. これらのリンクでは、次の **アクセス許可を付与できます:** サブウィンドウ 
    1. [ **ファイル** ] ドロップダウンリストから、 
        1. 認証されていないユーザーがファイルに変更を加えることを許可する場合は **、[表示と編集** ] を選択します。
        2. 認証されていないユーザーがファイルを変更できないようにする場合は、[ **表示** ] を選択します。
    2. [ **フォルダー** ] ボックスの一覧から、
        1. 認証されていないユーザーがフォルダーの変更を行えるようにする場合は、[ **表示、編集、およびアップロード** ] を選択します。
        2. 認証されていないユーザーがフォルダーを変更できないようにする場合は、[ **表示** ] を選択します。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint サイトレベルの共有設定

SharePoint サイト内のファイルとフォルダーを共有している場合は、そのサイトのサイトレベルの共有設定も確認する必要があります。

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

サイトレベルの共有設定を設定するには

1. SharePoint 管理センターの左側のナビゲーションウィンドウで、[ **サイト** ] を展開し、[ **アクティブなサイト**] をクリックします。
2. ゲストでファイルとフォルダーを共有するサイトを選択します。
3. 選択したサイトが表示されている行で右にスクロールし、[ **外部共有** ] 列の任意の場所をクリックします。
4. ポップアップ表示されたページで、[ **ポリシー** ] タブをクリックします。
5. [ **外部共有** ] ウィンドウで、[ **編集**] をクリックします。
6. 共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。
7. 変更を加えた場合は、[**保存**] をクリックします。

## <a name="invite-users"></a>ユーザーを招待する

ゲスト共有の設定が構成されるようになりました。これにより、ユーザーは、組織外のユーザーとファイルやフォルダーを共有できるようになります。 詳細については、「 [OneDrive ファイルとフォルダーを共有](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) する」および「 [SharePoint ファイルまたはフォルダーを共有](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) する」を参照してください。

## <a name="see-also"></a>関連項目

[認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)

[ゲストと共有するときにファイルの偶発的な公開を制限する](share-limit-accidental-exposure.md)

[Azure AD B2B を使用した SharePoint と OneDrive の統合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
