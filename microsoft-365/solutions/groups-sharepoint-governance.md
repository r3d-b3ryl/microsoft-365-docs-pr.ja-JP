---
title: Microsoft 365 グループと SharePoint の間の設定の相互作用
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループと SharePoint の間の設定の相互作用について説明します。
ms.openlocfilehash: e8d4189c2d945d5a6d2aa78bd7ea980a77360ce0
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377559"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 グループと SharePoint の間の設定の相互作用

Microsoft 365 グループおよび Microsoft 365 の SharePoint の一部の設定 (特に、共有とグループおよびチームサイトの作成に関連する) は、互いに重複しています。 この記事では、これらの相互作用と、これらの設定の使用方法に関するベストプラクティスについて説明します。

![SharePoint、Yammer、およびグループの機能のベン図](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Microsoft 365 グループへの SharePoint 設定の影響

|SharePoint の設定|説明|Microsoft 365 グループへの影響|推奨事項|
|:-----------------|:----------|:-----------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、およびフォルダーを組織外のユーザーと共有できるかどうかを決定します。|SharePoint とグループの設定が一致しない場合、グループのゲストはサイトへのアクセスをブロックされる可能性があります。また、外部アクセスはサイトでは使用できませんが、グループにはアクセスできない場合があります。|共有設定を変更するときは、グループの設定と、グループに接続されたチームサイトの SharePoint サイトの設定の両方を確認します。<br><br>「 [サイト内のゲストを使用して共同作業を](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)行う」を参照してください。|
|ドメイン許可/ブロック|指定したドメインとのコンテンツの共有を許可または禁止します。|グループは、SharePoint の許可または禁止リストを認識しません。 SharePoint で許可されていないドメインのユーザーが、グループを介して SharePoint にアクセスできる可能性があります。|Azure AD と SharePoint のドメインの許可/ブロック一覧を管理します。 ドメインを許可およびブロックするための、組織全体のガバナンスプロセスを作成します。<br><br>「 [SharePoint ドメインの設定](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)」および「 [Azure AD ドメインの設定](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)」を参照してください。|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可します。|サイト、フォルダー、およびファイルを外部で共有できるセキュリティグループを指定します。|この設定は、グループを外部で共有するグループの所有者には影響しません。 グループゲストは、関連付けられた SharePoint サイトにアクセスできます。||
|SharePoint サイトの共有設定|グループメンバーシップの外部にあるサイトを直接共有できるユーザーを決定します。 これは、グループまたはサイトの所有者によって構成されます。|この設定は、グループに直接影響を与えませんが、ユーザーをサイトに追加して、他のグループリソースにアクセス権を持たないようにすることができます。|この設定を使用してサイトの共有を直接制限し、グループを使用してサイトアクセスを管理することを検討してください。|
|ユーザーが SharePoint のスタートページおよび OneDrive からサイトを作成できるようにする|ユーザーが新しい SharePoint サイトを作成できるかどうかを指定します。|この設定を無効にした場合でも、グループを作成することで、グループに接続されたチームサイトを作成することができます。||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint での Microsoft 365 groups の設定の効果

|Microsoft 365 グループの設定|説明|SharePoint に対する影響|推奨事項|
|:---------------------------|:----------|:-------------------|:-------------|
|名前付けポリシー|グループの名前のプレフィックスとサフィックス、およびグループの作成に対してブロックする単語を指定します。|グループに接続されたチームサイトを作成するユーザーにはポリシーが適用されますが、他のテンプレートを使用して通信サイトやサイトを作成することはありません。|必要に応じて、コミュニケーションサイト用の別の命名ガイドを作成します。|
|グループのゲスト アクセス|組織外のユーザーをグループに追加できるかどうかを指定します。|SharePoint とグループの設定が一致しない場合、グループのゲストはサイトへのアクセスをブロックされる可能性があります。また、外部アクセスはサイトでは使用できませんが、グループにはアクセスできない場合があります。|共有設定を変更するときは、グループの設定と、グループに接続されたチームサイトの SharePoint サイトの設定の両方を確認します。<br><br>「[サイトでゲストと共同作業を](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)行う」を参照してください。|
|セキュリティグループによるグループの作成|グループは、特定のセキュリティグループのメンバーのみが作成できます。|セキュリティグループのメンバーではないユーザーは、グループに接続されたチームサイトを作成できません。|グループを要求するプロセスに、サイトを要求するための手順が含まれていることを確認してください。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除されるまでの期間を指定します。|グループが削除されると、関連付けられている SharePoint サイトも削除されます。 アイテム保持ポリシーによって保護されたコンテンツは保持されます。|有効期限ポリシーを使用して、未使用のグループとサイトが無秩序に増大しないようにします。|

## <a name="related-topics"></a>関連項目

[組織外のユーザーとの共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[SharePoint のサイト作成を管理する](https://docs.microsoft.com/sharepoint/manage-site-creation)