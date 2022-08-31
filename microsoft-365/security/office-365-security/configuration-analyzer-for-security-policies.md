---
title: セキュリティ ポリシーの構成アナライザー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、構成アナライザーを使用して、Standard protection および Strict Protection の設定の下にあるセキュリティ ポリシーを事前設定済みのセキュリティ ポリシーで見つけて修正する方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b5f33bb7b30f63ad5d6705b7a9cbffb38f280a2c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479161"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP および Defender for Office 365 の構成アナライザー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルの構成アナライザーは、[設定が事前設定](preset-security-policies.md)されたセキュリティ ポリシーの Standard Protection および Strict Protection プロファイル設定の下にあるセキュリティ ポリシーを検索して修正するための一元的な場所を提供します。

次の種類のポリシーは、構成アナライザーによって分析されます。

- **Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。
  - [スパム対策ポリシー](configure-your-spam-filter-policies.md)。
  - [マルウェア対策ポリシー](configure-anti-malware-policies.md)。
  - [EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender for Office 365 ポリシー**: これには、Microsoft 365 E5またはDefender for Office 365アドオン サブスクリプションを持つ組織が含まれます。
  - Microsoft Defender for Office 365のフィッシング対策ポリシー。
    - EOP フィッシング対策ポリシーで使用できるのと同じ [スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings) 。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [安全なリンク ポリシー](set-up-safe-links-policies.md)。
  - [安全な添付ファイル ポリシー](set-up-safe-attachments-policies.md)。

ベースラインとして使用される Standard および Strict ポリシー設定の値については、「[EOP とMicrosoft Defender for Office 365セキュリティの推奨設定」を参照](recommended-settings-for-eop-and-office365.md)してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[構成アナライザー]** ページに直接移動するには、 <https://security.microsoft.com/configurationAnalyzer>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Microsoft 365 Defender ポータルでアクセス許可を割り当てる必要があります。
  - 構成アナライザーを使用 **して** セキュリティ ポリシーを更新するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 構成アナライザーへの読み取り専用アクセスを行うには、**グローバル リーダー** または **セキュリティ リーダー** の役割グループのメンバーである必要があります。

  詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

  > [!NOTE]
  >
  > - 対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可 _と_、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで構成アナライザーを使用する

Microsoft 365 Defender ポータルの [**テンプレート** ポリシー] セクション **の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **構成アナライザー**] に移動します。 **[構成アナライザー]** ページに直接移動するには、 <https://security.microsoft.com/configurationAnalyzer>.

**[構成アナライザー]** ページには、次の 3 つのメイン タブがあります。

- **標準の推奨事項**: 既存のセキュリティ ポリシーを標準の推奨事項と比較します。 設定値を調整して、Standard と同じレベルに設定することができます。
- **厳密な推奨事項**: 既存のセキュリティ ポリシーと厳密な推奨事項を比較します。 設定値を調整して、Strict と同じレベルに設定することができます。
- **構成ドリフト分析と履歴**: 時間の経過と共にポリシーの変更を監査および追跡します。

### <a name="standard-recommendations-and-strict-recommendations-tabs-in-the-configuration-analyzer"></a>構成アナライザーの [標準の推奨事項] タブと [厳密な推奨事項] タブ

既定では、構成アナライザーは [ **標準の推奨事項** ] タブで開きます。 **[厳密な推奨事項** ] タブに切り替えることができます。設定、レイアウト、アクションは両方のタブで同じです。

:::image type="content" source="../../media/configuration-analyzer-settings-and-recommendations-view.png" alt-text="構成アナライザーの [設定と推奨事項] ビュー" lightbox="../../media/configuration-analyzer-settings-and-recommendations-view.png":::

タブの最初のセクションには、Standard または Strict 保護と比較して改善が必要なポリシーの種類ごとの設定の数が表示されます。 ポリシーの種類は次のとおりです。

- **スパム対策**
- **フィッシング詐欺対策**
- **マルウェア対策**
- **安全な添付ファイル** (サブスクリプションにMicrosoft Defender for Office 365が含まれている場合)
- **安全なリンク** (サブスクリプションにMicrosoft Defender for Office 365が含まれている場合)

ポリシーの種類と番号が表示されない場合は、その種類のすべてのポリシーが Standard または Strict 保護の推奨設定を満たします。

タブの残りの部分は、Standard または Strict の保護レベルに設定する必要がある設定のテーブルです。 テーブルには、次の列が含まれています。

- **推奨事項**: 標準または厳格な保護プロファイルの設定の値。
- **ポリシー**: 設定を含む影響を受けるポリシーの名前。
- **ポリシー グループ/設定名**: 注意が必要な設定の名前。
- **ポリシーの種類**: スパム対策、フィッシング詐欺対策、マルウェア対策、安全なリンク、または安全な添付ファイル。
- **現在の構成**: 設定の現在の値。
- **最終更新日**: ポリシーが最後に変更された日付。
- **状態**: 通常、この値は **開始されません**。

### <a name="change-a-policy-setting-to-the-recommended-value"></a>ポリシー設定を推奨値に変更する

構成アナライザーの [ **標準保護** ] タブまたは [ **Strict Protection** ] タブで、テーブル内の行を選択します。 次のボタンが表示されます。

- **推奨事項を適用する**
- **ポリシーを表示する**
- **更新**:

行を選択して [推奨事項の **適用**] をクリックすると、確認ダイアログ (ダイアログを再び表示しないオプションを含む) が表示されます。 **[OK] を** クリックすると、次のことが発生します。

- 設定が推奨値に更新されます。
- **[推奨事項の適用]** **ポリシーと [表示] ポリシー** が消えます (**[更新]** ボタンのみが残ります)。
- 行の **[状態]** の値が **[完了]** に変わります。

行を選択し、[ポリシーの **表示**] をクリックすると、Microsoft 365 Defender ポータルで影響を受けるポリシーの詳細ポップアップが表示され、設定を手動で更新できます。

設定を自動的または手動で更新したら、[ **更新** ] をクリックして、推奨事項の数が減り、更新された行が結果から削除されたことを確認します。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>構成アナライザーの構成ドリフト分析と履歴タブ

このタブでは、セキュリティ ポリシーに加えられた変更と、それらの変更が Standard または Strict の設定とどのように比較されるかを追跡できます。 既定では、次の情報が表示されます。

- **最終更新日時**
- **変更者**
- **名前の設定**
- **ポリシー**: 影響を受けるポリシーの名前。
- **種類**: スパム対策、フィッシング詐欺対策、マルウェア対策、安全なリンク、または安全な添付ファイル。
- **構成の変更**: 古い値と設定の新しい値
- **構成ドリフト**: 推奨される **Standard または Strict** の設定と比較して、設定のセキュリティの増減を示す値 **[増減**] を指定します。

結果をフィルター処理するには、**[フィルター]** をクリックします。 表示される **[フィルター]** ポップアップで、次のフィルターから選択できます。

- **開始時刻** と **終了時刻** (日付): 今日から 90 日間まで戻ることができます。
- **標準保護** または **厳格な保護**

完了したら、**[適用]** をクリックします。

結果を.csv ファイルにエクスポートするには、[ **エクスポート**] をクリックします。

特定の **変更者**、 **設定名**、または **種類** の値で結果をフィルター処理するには、[ **検索** ] ボックスを使用します。

:::image type="content" source="../../media/configuration-analyzer-configuration-drift-analysis-view.png" alt-text="Configuration アナライザーの構成ドリフト分析と履歴ビュー" lightbox="../../media/configuration-analyzer-configuration-drift-analysis-view.png":::
