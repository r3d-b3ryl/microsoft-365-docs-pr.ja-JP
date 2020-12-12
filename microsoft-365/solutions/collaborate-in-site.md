---
title: サイトでゲストと共同で作業する
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
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: ゲストとの共同作業用に SharePoint サイトをセットアップするために必要な Microsoft 365 構成手順について説明します。
ms.openlocfilehash: 6862fe715fe2f19b968b773bc6df6c70c207a44f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663526"
---
# <a name="collaborate-with-guests-in-a-site"></a>サイトでゲストと共同で作業する

ドキュメント、データ、およびリスト間でゲストと共同作業する必要がある場合は、SharePoint サイトを使用できます。 最新の SharePoint サイトは Microsoft 365 グループに接続され、サイト メンバーシップを管理し、共有メールボックスや予定表などの追加のコラボレーション ツールを提供できます。

この記事では、ゲストとの共同作業用に SharePoint サイトをセットアップするために必要な Microsoft 365 構成手順について説明します。

## <a name="video-demonstration"></a>ビデオ デモンストレーション

このビデオでは、このドキュメントで説明されている構成手順を示します。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部コラボレーションの設定

Microsoft 365 での共有は、Azure Active Directory の B2B 外部コラボレーション設定によって最高レベル [で管理されます](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)。 Azure AD でゲスト共有が無効または制限されている場合、この設定は Microsoft 365 で構成した共有設定より優先されます。

B2B 外部コラボレーション設定を確認して、ゲストとの共有がブロックされていないか確認します。

![[Azure Active Directory 外部コラボレーションの設定] ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

外部コラボレーション設定を設定するには

1. Azure Active Directory にログインします [https://aad.portal.azure.com](https://aad.portal.azure.com) 。
2. 左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。
3. [外部 **ID] をクリックします**。
4. [作業の **開始] 画面** の左側のナビゲーション ウィンドウで、[外部コラボレーションの設定 **] をクリックします**。
5. 管理者と **ゲスト招待者の役割のユーザーが** 招待可能であり、 **メンバー** が招待可能な両方が [はい] **に設定されています**。
6. 変更を加えた場合は、[**保存**] をクリックします。

[コラボレーションの制限] セクション **の設定に注意** してください。 共同作業を行うゲストのドメインがブロックされていないか確認します。

複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスする機能を制限できます。 これにより、他のユーザーがディレクトリのゲストであるのを見るのを防ぐのに使用できます。 これを行うには、[ゲストユーザーのアクセス制限]で、[ゲスト ユーザーがプロパティへのアクセス権とディレクトリ オブジェクト設定のメンバーシップに制限されている] を選択するか、[ゲスト **ユーザー** アクセス] を自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限します。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 グループのゲスト設定

モダン SharePoint サイトでは、Microsoft 365 グループを使用してサイトアクセスを制御します。 SharePoint サイトでゲスト アクセスを機能するには、Microsoft 365 グループのゲスト設定を有効にする必要があります。

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

Microsoft 365 グループのゲスト設定を設定するには

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[設定] を **展開します**。
2. [ **組織の設定] をクリックします**。
3. 一覧で **、[Microsoft 365 グループ] をクリックします**。
4. [グループ所有者が組織外のユーザーをゲストとして **Microsoft 365 グループ** に追加する] チェック ボックスと [ゲスト グループ のメンバーがグループ コンテンツにアクセスする] の両方のチェック ボックスがオンになっています。
5. 変更を加えた場合は、[変更の保存] **をクリックします**。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織レベルの共有設定

ゲストが SharePoint サイトにアクセスするには、SharePoint 組織レベルの共有設定でゲストとの共有を許可する必要があります。

組織レベルの設定によって、個々のサイトで使用できる設定が決なります。 サイトの設定を組織レベルの設定よりも制限することはできません。

認証されていないファイルとフォルダーの共有を許可する場合は、[すべてのユーザー] を選択 **します**。 組織外のすべてのユーザーが認証を行う必要がある場合は、[新規および既存のゲスト] **を選択します**。 組織内の任意のサイトで必要になる最も制限の多い設定を選択します。

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 組織レベルの共有設定を設定するには

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、[管理センター] の下の **[SharePoint] をクリックします**。
2. SharePoint 管理センターの左側のナビゲーション ウィンドウで、[ポリシー ] の下の [共有] を **クリックします**。
3. SharePoint の外部共有が [すべてのユーザー] または [新規] および [既存の **ゲスト] に設定されている必要があります**。
4. 変更を加えた場合は、[**保存**] をクリックします。

## <a name="create-a-site"></a>サイトを作成する

次の手順では、ゲストとの共同作業に使用する予定のサイトを作成します。

サイトを作成するには
1. SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。
2. **[作成]** をクリックします。
3. [チーム **サイト] をクリックします**。
4. サイト名を入力し、グループ所有者 (サイト所有者) の名前を入力します。
5. [ **詳細設定] で**、このサイトをパブリックサイトにするか、プライベートサイトにするか選択します。
6. [ **次へ**] をクリックします。
7. [**完了**] をクリックします。

後でユーザーを招待します。 次に、このサイトのサイト レベルの共有設定を確認することが重要です。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint サイト レベルの共有設定

サイト レベルの共有設定を確認して、このサイトに必要なアクセスの種類を許可します。 たとえば、組織レベルの設定を **[** すべてのユーザー] に設定し、すべてのゲストに対してこのサイトの認証を行う場合は、サイト レベルの共有設定が [新規] および [既存のゲスト] に設定されている必要 **があります。**

サイトを認証されていないユーザー **([** すべてのユーザー] 設定) と共有することはできませんが、個々のファイルとフォルダーは共有できます。

また、SharePoint サイト [の外部共有設定を制御するために、区別ラベルを使用することもできます](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

サイト レベルの共有設定を設定するには
1. SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。
2. 共有するサイトを選択します。
3. [...] をクリックし、[共有] を **クリックします**。
4. 共有が [すべてのユーザー] または **[新規** ] および [ **既存のゲスト] に設定されている必要があります**。
5. 変更を加えた場合は、[**保存**] をクリックします。

## <a name="invite-users"></a>ユーザーを招待する

ゲスト共有設定が構成されたので、内部ユーザーとゲストをサイトに追加できます。 サイト アクセスは、関連付けられた Microsoft 365 グループを通じて制御されます。そのため、そこにユーザーを追加します。

内部ユーザーをグループに招待するには
1. ユーザーを追加するサイトに移動します。
2. 右上 **の** [メンバー] リンク (メンバー数を示す) をクリックします。
3. **[メンバーの追加]** をクリックします。
4. サイトに招待するユーザーの名前または電子メール アドレスを入力し、[保存] をクリック **します**。

ゲストをサイトから追加できない。 Outlook on the web を使用して追加する必要があります。 そのため、ゲストを追加してグループに招待する前提条件として、[URL] 列でサイトの URLをクリックして、サイト固有のページに移動します。 このページで、[アプリ起動ツール] アイコン **を** クリックし **、[Outlook] を選択します**。 これは、グループにゲストを招待できる画面で、以下に示す手順について説明します。

ゲストをグループに招待するには
1. [ **グループ]** で、ゲストを招待するグループをクリックします。
2. グループ連絡先カードを開き、右上の [メンバー] リンク (メンバー数を示すリンク) をクリックします。
3. [メンバー **の追加] をクリックします**。
4. 招待するゲストのメール アドレスを入力し、[追加] をクリック **します**。
5. [閉じる] をクリックします。
[閉じる] をクリックする必要があるのは、ユーザーがグループの所有者ではなく、その結果、グループにゲストを追加できない場合のみです。 このような場合、グループにゲストを追加する要求は、承認のためにグループの所有者に転送されます。

## <a name="see-also"></a>関連項目

[認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)

[ゲストと共有するときにファイルの偶発的な公開を制限する](share-limit-accidental-exposure.md)

[セキュリティで保護されたゲスト共有環境を作成する](create-secure-guest-sharing-environment.md)

[管理されたゲストで B2B エクストラネットを作成する](b2b-extranet.md)

[SharePoint と OneDrive と Azure AD B2B の統合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
