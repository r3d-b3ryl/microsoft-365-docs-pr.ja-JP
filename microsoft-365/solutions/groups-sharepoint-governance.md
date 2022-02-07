---
title: Microsoft 365 グループと SharePoint 間の設定の相互作用
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
  - M365-collaboration
  - m365solution-collabgovernance
ms.custom:
  - M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 グループと SharePoint 間の設定の相互作用の概要
---

# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 グループと SharePoint 間の設定の相互作用

Microsoft 365 の Microsoft 365 グループと SharePoint の一部の設定 (特に共有、グループ、チーム サイトの作成に関連した部分) は、互いに重複しています。 この記事では、これらの相互作用の説明と、これらの設定を操作する方法のベスト プラクティスについて説明します。

![SharePoint、Yammer、グループ機能のベン図表。](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>SharePoint 設定が Microsoft 365 グループに及ぼす効果

|SharePoint の設定|説明|Microsoft 365 グループに及ぼす効果|推奨事項|
|:-----------------|:----------|:-----------------------------|:-------------|
|組織とサイトの外部共有|サイト、ファイル、フォルダーを組織外のユーザーと共有できるかどうかを決定します。|SharePoint とグループの設定が一致しない場合、グループ内のゲストがサイトへのアクセスをブロックされているか、外部アクセスがサイトでは利用できても、グループでは利用できない可能性があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定と SharePoint サイトの設定の両方を確認します。<br><br>「[サイトでゲストと共同作業する](./collaborate-in-site.md)」を参照してください。|
|ドメインの許可/ブロック|指定したドメインとのコンテンツの共有を許可または禁止します。|グループは SharePoint 許可リストまたはブロックリストを認識しません。 SharePoint で許可されていないドメインのユーザーは、グループを通じて SharePoint にアクセスできます。|Azure AD と SharePoint のドメイン許可リストまたはブロック リストを一緒に管理します。 ドメインを許可およびブロックするための組織全体のガバナンス プロセスを作成します。<br><br>「[SharePoint ドメイン設定](/sharepoint/restricted-domains-sharing)」と「[Azure AD ドメイン設定](/azure/active-directory/b2b/allow-deny-list)」を参照してください|
|特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可する|サイト、フォルダー、およびファイルを外部と共有できるセキュリティ グループを指定します。|この設定は、外部でグループを共有するグループ所有者には影響しません。 グループ ゲストは、関連付けられている SharePoint サイトにアクセスできます。||
|SharePoint サイトの共有設定|グループ メンバーシップの外部でサイトを直接共有できるユーザーを決定します。 これは、グループまたはサイトの所有者によって構成されます。|この設定はグループに直接影響しませんが、ユーザーをサイトに追加し、他のグループ リソースにアクセスできないようにすることができます|この設定を使用して、サイトの直接共有を制限し、グループを介したサイト アクセスを管理することを検討してください。|
|ユーザーが SharePoint スタート ページと OneDrive からサイトを作成できるようにする|ユーザーが新しい SharePoint サイトを作成できるかどうかを指定します。|この設定をオフにした場合でも、ユーザーはグループを作成することでグループに接続されたチーム サイトを作成できます。||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint でのMicrosoft 365 グループ設定の効果

|Microsoft 365 グループの設定|説明|SharePoint に対する効果|推奨事項|
|:---------------------------|:----------|:-------------------|:-------------|
|名前付けポリシー|グループ名のプレフィックスとサフィックス、およびグループ作成時にブロックされる単語を指定します|ポリシーは、グループに接続されたチーム サイトを作成するユーザーに適用されますが、コミュニケーション サイトや他のテンプレートを持つサイトには適用されません。|必要に応じて、コミュニケーション サイト用に個別の名前付けに関するガイダンスを作成します。|
|グループのゲスト アクセス|組織外のユーザーをグループに追加できるかどうかを指定します。|SharePoint とグループの設定が一致しない場合、グループ内のゲストがサイトへのアクセスをブロックされているか、外部アクセスがサイトでは利用できても、グループでは利用できない可能性があります。|共有設定を変更する場合は、グループに接続されたチーム サイトのグループ設定と SharePoint サイトの設定の両方を確認します。<br><br>「[サイトでゲストと共同で作業する](./collaborate-in-site.md)」を参照してください|
|セキュリティ グループ別のグループ作成|特定のセキュリティ グループのメンバーのみがグループを作成できます。|セキュリティ グループのメンバーではないユーザーは、グループに接続されたチーム サイトを作成できません。|グループを要求するプロセスに、サイトを要求するための手順が含まれていることを確認してください。|
|グループの有効期限ポリシー|アクティブに使用されていないグループが自動的に削除される期間を指定します。|グループが削除されると、関連付けられている SharePoint サイトも削除されます。 アイテム保持ポリシーによって保護されているコンテンツは保持されます。|有効期限ポリシーを使用して、未使用のグループとサイトが増加しないようにします。|

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[組織外部のユーザーとの共有](./collaborate-with-people-outside-your-organization.md)

[SharePoint のサイト作成を管理する](/sharepoint/manage-site-creation)