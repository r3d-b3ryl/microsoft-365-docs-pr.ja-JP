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
- admindeeplinkSPO
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: ゲストとのコラボレーションのために SharePoint サイトを設定するために必要な Microsoft 365 構成手順について説明します。
ms.openlocfilehash: 6814eb2dd1d0876c332a7be932fc8c59a43f198c
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67344649"
---
# <a name="collaborate-with-guests-in-a-site"></a>サイトでゲストと共同で作業する

ドキュメント、データ、リスト間でゲストと共同作業する必要がある場合は、SharePoint サイトを使用できます。 最新の SharePoint サイトはMicrosoft 365 グループに接続されており、サイト メンバーシップを管理し、共有メールボックスや予定表などの追加のコラボレーション ツールを提供できます。

この記事では、ゲストとのコラボレーションのために SharePoint サイトを設定するために必要な Microsoft 365 構成手順について説明します。

## <a name="video-demonstration"></a>ビデオ デモンストレーション

このビデオは、このドキュメントで説明されている構成手順を示しています。</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure 外部コラボレーション設定

Microsoft 365 での共有は、[Azure Active Directory における B2B 外部コラボレーションの設定](/azure/active-directory/external-identities/delegate-invitations) によって最高レベルで管理されます。 Azure AD でゲストの共有が無効になっているか、制限されている場合、この設定により、Microsoft 365 で構成した共有設定が上書きされます。

B2B 外部コラボレーションの設定をチェックして、ゲストとの共有がブロックされていないことを確認します。

![Azure Active Directory の [外部コラボレーションの設定] ページのスクリーンショット。](../media/azure-ad-organizational-relationships-settings.png)

外部コラボレーションを設定するには

1. [https://aad.portal.azure.com](https://aad.portal.azure.com) で Azure Active Directory にログインします。
2. 左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。
3. **[外部 ID]** をクリックします。
4. **[開始]** 画面で、左側のナビゲーション ウィンドウで **[外部コラボレーション設定]** をクリックします。
5. 特定の **管理者ロールに割り当てられたメンバー ユーザーとユーザーが、メンバーアクセス許可を持つゲストを含むゲスト ユーザーを招待できるか**、**組織内のユーザーがゲストを含むゲスト ユーザーを招待し、管理者以外のユーザー** を招待できます。
6. 変更を加えた場合は、**[保存]** をクリックします。

**[共同作業の制限]** セクションの設定に注意してください。 共同作業するゲストのドメインがブロックされていないことを確認します。

複数の組織のゲストと連携する場合は、ディレクトリ データにアクセスするゲストの機能を制限することをお勧めします。 これにより、他に誰がディレクトリ内のゲストであるかを確認できなくなります。 これを行うには、**[ゲスト ユーザーのアクセス制限]** で、**[ゲスト ユーザーはディレクトリ オブジェクト設定のプロパティとメンバーシップに制限付きアクセス権が付与されている]** または **[ゲスト ユーザーのアクセスは自分のディレクトリ オブジェクトのプロパティとメンバーシップに制限されている]** を選択します。

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 グループのゲスト設定

最新の SharePoint サイトでは、Microsoft 365 グループを使用してサイト へのアクセスを制御します。 SharePoint サイトのゲスト アクセスを機能させるには、Microsoft 365 グループゲスト設定を有効にする必要があります。

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット。](../media/office-365-groups-guest-settings.png)

Microsoft 365 グループのゲスト設定を行うには

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**[設定]** を展開します。
2. **[組織の設定]** をクリックします。
3. 一覧で、**[Microsoft 365 グループ]** をクリックします。
4. **[組織外のグループ所有者に Microsoft 365 グループへのアクセスを許可する]** と **[グループ メンバーにグループ コンテンツへのアクセスを許可する]** チェック ボックスが両方ともオンになっていることを確認します。
5. 変更を加えた場合は、**[変更の保存]** をクリックします。

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint 組織レベルの共有設定

ゲストが SharePoint サイトにアクセスできるようにするには、SharePoint 組織レベルの共有設定でゲストとの共有を許可する必要があります。

組織レベルの設定によって、個々のサイトで使用できる設定が決まります。 サイトの設定は、組織レベルの設定よりも制限を緩和することはできません。

認証されていないファイルとフォルダーの共有を許可する場合は、[ **すべてのユーザー**] を選択します。 組織外のすべてのユーザーが認証する必要があることを確認する場合は、[ **新規ゲストと既存のゲスト**] を選択します。 組織内の任意のサイトで必要となる最も制限が少ない設定を選択します。

![SharePoint 組織レベルの共有設定のスクリーンショット。](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint 組織レベルの共有設定を設定するには

1. Microsoft 365 管理センターの左側のナビゲーション ウィンドウで、**管理センター** で **SharePoint** を選択します。
2. SharePoint 管理センターの左側のナビゲーション ウィンドウの [ **ポリシー**] で、[ <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**共有**</a>] を選択します。
3. SharePoint の外部共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。
4. 変更した場合は、**[保存]** を選択します。

## <a name="create-a-site"></a>サイトを作成する

次の手順では、ゲストとの共同作業に使用する予定のサイトを作成します。

サイトを作成するには
1. SharePoint 管理センターの **[サイト]** で、<a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**[アクティブなサイト]**</a> を選択します。
2. **[作成]** を選択します。
3. [ **チーム サイト] を選択します**。
4. サイト名を入力し、グループ所有者 (サイト所有者) の名前を入力します。
5. [ **詳細設定]** で、このサイトをパブリックまたはプライベートのどちらにするかを選択します。
6. **[次へ]** を選択します。
7. **[完了]** を選択します。

後でユーザーを招待します。 次に、このサイトのサイト レベルの共有設定を確認することが重要です。

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint のサイト レベル共有設定のスクリーンショット

サイト レベルの共有設定を確認して、このサイトに必要なアクセスの種類が許可されていることを確認します。 たとえば、組織レベルの設定を **[すべてのユーザー**] に設定し、すべてのゲストがこのサイトの認証を行う場合は、サイト レベルの共有設定が **[新規] と [既存のゲスト**] に設定されていることを確認します。

サイトを認証されていないユーザー (**[すべての** ユーザー] 設定) と共有することはできませんが、個々のファイルとフォルダーで共有できることに注意してください。

[秘密度ラベルを使用して、SharePoint サイトの外部共有設定を制御](../compliance/sensitivity-labels-teams-groups-sites.md)することもできます。

![SharePoint サイトの外部共有設定のスクリーンショット。](../media/sharepoint-site-external-sharing-settings.png)

サイトレベルの共有設定を設定するには
1. SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [<a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**アクティブなサイト**</a>] を選択します。
2. 共有するサイトを選択します。
3. [...] を選択し、[ **共有**] を選択します。
4. 共有が **[全員]** または **[新規および既存のゲスト]** に設定されていることを確認します。
5. 変更した場合は、**[保存]** を選択します。

## <a name="invite-users"></a>ユーザーを招待する

ゲスト共有設定が構成され、サイトへの内部ユーザーとゲストの追加を開始できるようになりました。 サイト へのアクセスは、関連付けられた Microsoft 365 グループを介して制御されるため、ユーザーを追加します。

内部ユーザーをグループに招待するには

1. ユーザーを追加するサイトに移動します。
2. 右上の **[メンバー** の数] リンクを選択します。
3. [**メンバーの追加**] を選択します。
4. サイトに招待するユーザーの名前または電子メール アドレスを入力し、[保存] を選択 **します**。

サイトから Microsoft 365 グループにゲストを追加することはできません。 グループにゲストを追加する方法については、「[Microsoft 365 グループへのゲストの追加」を](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)参照してください。

## <a name="see-also"></a>関連項目

[認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス](best-practices-anonymous-sharing.md)

[ゲストと共有するときにファイルの偶発的な公開を制限する](share-limit-accidental-exposure.md)

[セキュリティで保護されたゲスト共有の環境を作成する](create-secure-guest-sharing-environment.md)

[管理されたゲストで B2B エクストラネットを作成する](b2b-extranet.md)

[SharePoint および OneDrive の Azure AD B2B との統合](/sharepoint/sharepoint-azureb2b-integration-preview)
