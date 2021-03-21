---
title: Microsoft 365 グループと SharePoint の間の設定操作
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
description: Microsoft 365 グループと SharePoint の間の設定の操作について説明します。
ms.openlocfilehash: e1aeaca792fb551de503bd4c68256ccf14f45022
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921038"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 グループと SharePoint の間の設定操作

Microsoft 365 の Microsoft 365 グループと SharePoint の設定の中には、特に共有とグループサイトとチーム サイトの作成に関連する設定が重複しています。 この記事では、これらの設定を操作する方法に関するこれらの操作とベスト プラクティスについて説明します。

![SharePoint、Yammer、およびグループの機能のベン図](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Microsoft 365 グループに対する SharePoint 設定の影響

|SharePoint の設定|説明|Microsoft 365 グループへの影響|推奨事項|
|:-----------------|:----------|:-----------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、フォルダーを組織外のユーザーと共有できるかどうかを指定します。|SharePoint とグループの設定が一致しない場合は、グループ内のゲストがサイトへのアクセスをブロックされる場合や、サイトで外部アクセスを利用できますが、グループではアクセスできない場合があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定と SharePoint サイト設定の両方を確認します。<br><br>「サイト [内のゲストと共同作業する」を参照してください](./collaborate-in-site.md)。|
|ドメインの許可/ブロック|指定したドメインとコンテンツが共有されるのを許可または防止します。|グループは SharePoint 許可リストまたはブロック リストを認識しない。 SharePoint で禁止されているドメインのユーザーは、グループを介して SharePoint にアクセスできます。|Azure ADおよび SharePoint のドメイン許可/ブロックリストを一緒に管理します。 ドメインを許可およびブロックする組織全体のガバナンス プロセスを作成します。<br><br>[「SharePoint ドメイン設定」および](/sharepoint/restricted-domains-sharing)[「Azure ドメイン設定AD」を参照してください。](/azure/active-directory/b2b/allow-deny-list)|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可します。|サイト、フォルダー、およびファイルを外部で共有できるセキュリティ グループを指定します。|この設定は、グループの所有者がグループを外部で共有する場合には影響を与えかねない。 グループ ゲストは、関連付けられた SharePoint サイトにアクセスできます。||
|SharePoint サイト共有設定|グループ メンバーシップの外部でサイトを直接共有できるユーザーを指定します。 これは、グループまたはサイトの所有者によって構成されます。|この設定はグループに直接影響を与えるものではありませんが、ユーザーがサイトに追加され、他のグループ リソースにアクセスできない場合があります。|この設定を使用して、サイトの共有を直接制限し、グループを通じてサイト アクセスを管理する方法を検討してください。|
|SharePoint スタート ページと OneDrive からサイトを作成する|ユーザーが新しい SharePoint サイトを作成できる場合に指定します。|この設定をオフにした場合でも、ユーザーはグループを作成することでグループに接続されたチーム サイトを作成できます。||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint での Microsoft 365 グループ設定の影響

|Microsoft 365 グループの設定|説明|SharePoint への影響|推奨事項|
|:---------------------------|:----------|:-------------------|:-------------|
|名前付けポリシー|グループ名のプレフィックスとサフィックス、およびグループ作成のブロックされた単語を指定します。|ポリシーは、グループに接続されたチーム サイトを作成するユーザーに適用されますが、他のテンプレートとの通信サイトやサイトには適用されません。|必要に応じて、通信サイトの個別の名前付けガイダンスを作成します。|
|グループのゲスト アクセス|組織外のユーザーをグループに追加できる場合に指定します。|SharePoint とグループの設定が一致しない場合は、グループ内のゲストがサイトへのアクセスをブロックされる場合や、サイトで外部アクセスを利用できますが、グループではアクセスできない場合があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定と SharePoint サイト設定の両方を確認します。<br><br>「サイト [内のゲストと共同作業する」を参照してください。](./collaborate-in-site.md)|
|セキュリティ グループによるグループ作成|グループを作成できるのは、特定のセキュリティ グループのメンバーのみです。|セキュリティ グループのメンバーではないユーザーは、グループに接続されたチーム サイトを作成できます。|グループを要求するプロセスに、サイトを要求する手順が含まれています。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除される期間を指定します。|グループを削除すると、関連付けられた SharePoint サイトも削除されます。 アイテム保持ポリシーによって保護されたコンテンツは保持されます。|有効期限ポリシーを使用して、未使用のグループとサイトの広がりを回避します。|

## <a name="related-topics"></a>関連項目

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md)

[組織外部のユーザーとの共有](./collaborate-with-people-outside-your-organization.md)

[SharePoint のサイト作成を管理する](/sharepoint/manage-site-creation)