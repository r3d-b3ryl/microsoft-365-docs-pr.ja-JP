---
title: セキュリティ ポリシー用の構成アナライザー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準の保護と厳密な保護の事前設定セキュリティ ポリシーの下にあるセキュリティ ポリシーを見つけて修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029480"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP および Microsoft Defender for Office 365 の保護ポリシーの構成アナライザー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


セキュリティ & コンプライアンス センターの構成アナライザーは、あらかじめ設定されているセキュリティ ポリシーの [標準の保護] および [厳密な保護] プロファイル設定の下にあるセキュリティ ポリシーを検索して修正するための一中心の場所を [提供](preset-security-policies.md)します。

次の種類のポリシーが構成アナライザーによって分析されます。

- **Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロンの EOP 組織が含まれます。

  - [スパム対策ポリシー](configure-your-spam-filter-policies.md)。
  - [マルウェア対策ポリシー](configure-anti-malware-policies.md)。
  - [EOP フィッシング詐欺対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender for Office 365 アドオン サブスクリプションを持つ組織が含まれます。

  - Microsoft Defender for Office 365 のフィッシング対策ポリシー。次のものが含まれます。

    - EOP [フィッシング詐欺](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用可能なスプーフィング設定と同じ。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [安全なリンク ポリシー](set-up-atp-safe-links-policies.md)。

  - [安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)。

ベースライン **として使用** される Standard および **Strict** ポリシー設定の値については [、「365](recommended-settings-for-eop-and-office365-atp.md)セキュリティのための EOP と Microsoft Defender の推奨Office説明されています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [構成アナライザー] ページに **直接移動するには** 、次の値を使用します <https://protection.office.com/configurationAnalyzer> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:
  - 構成アナライザーを使用して **セキュリティ** ポリシーを更新するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - 構成アナライザーに読み取り専用でアクセスするには、グローバル閲覧者役割グループまたはセキュリティ閲覧者役割グループのメンバー **である** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  > [!NOTE]
  >  
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  > 
  > - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターで構成&使用する

セキュリティ/コンプライアンス センター&、脅威管理 **ポリシー構成** アナライザー \> **に** \> **移動します**。

![[脅威管理ポリシー] ページの Configuration \> Analyzer ウィジェット](../../media/configuration-analyzer-widget.png)

構成アナライザーには、次の 2 つのメイン タブがあります。

- **設定と推奨事項**: [標準] または [厳密] を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。 結果では、設定の値を調整して、Standard または Strict と同じレベルに設定できます。

- **構成の流れ分析と履歴**: このビューでは、ポリシーの変更を時間の中で追跡できます。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>構成アナライザーの [設定と推奨事項] タブ

既定では、標準保護プロファイルとの比較でタブが開きます。 [厳密な保護] プロファイルの比較に切り替えるには、[厳密な推奨事項の表示] **をクリックします**。 戻る場合は、[標準おすすめ **の表示] を選択します**。

![構成アナライザーの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

既定では、[ポリシー グループ **/** 設定名] 列には、さまざまな種類のセキュリティ ポリシーの折りたたまれているビューと、改善が必要な設定の数が表示されます (その場合)。 ポリシーの種類は次のとおりです。

- **スパム対策**
- **フィッシング詐欺対策**
- **マルウェア対策**
- **ATP の安全な添付** ファイル (サブスクリプションに microsoft Defender for Office 365 が含まれる場合)
- **ATP の安全なリンク** (サブスクリプションに microsoft Defender for Office 365 が含まれる場合)

既定のビューでは、すべて折りたためます。 各ポリシーの横には、ポリシー (変更可能) と、Standard または Strict 保護プロファイルの対応するポリシーの設定 (変更できない) からの比較結果の概要があります。 比較している保護プロファイルに関する次の情報が表示されます。

- **緑**: すべての既存のポリシーのすべての設定は、少なくとも保護プロファイルと同じほど安全です。
- **固定**: 既存のポリシーの設定の数が少ない場合、保護プロファイルほど安全ではありません。
- **赤**: 既存のポリシーの設定の数が多く、保護プロファイルほど安全ではありません。 これは、多くのポリシーのいくつかの設定、または 1 つのポリシーの多くの設定である可能性があります。

好ましい比較を行う場合は、「すべての設定が推奨事項に従っている」 **というテキスト** \<**Standard** or **Strict**\> **が表示されます**。 それ以外の場合は、変更する推奨設定の数が表示されます。

[ポリシー グループ **/** 設定名] を展開すると、注意が必要な各特定のポリシーのすべてのポリシーと関連する設定が表示されます。 または、特定の種類のポリシー (スパム **対策など)** を展開して、注意が必要なポリシーの種類の設定を表示することもできます。

比較に改善のための推奨事項 (緑色) がない場合、ポリシーを展開すると何も表示されなにもありません。 改善のための推奨事項が何件かある場合 (注目または赤)、注意が必要な設定が表示され、次の列に対応する情報が表示されます。

- 注意が必要な設定の名前。 たとえば、前のスクリーンショットでは、スパム対策ポリシー **のバルク** メールしきい値です。

- **ポリシー**: 設定を含む影響を受けるポリシーの名前。

- **適用:** 影響を受けるポリシーが適用されるユーザーの数。

- **現在の構成**: 設定の現在の値。

- **最終更新日:** ポリシーが最後に変更された日付。

- **推奨事項**: Standard または Strict 保護プロファイルの設定の値。 ポリシーの設定の値を保護プロファイルの推奨値と一致する値に変更するには、[導入] をクリック **します**。 変更が成功すると、「Recommendations **successfully adopted**」というメッセージが表示されます。 [ **最新の** 情報に更新] をクリックすると、推奨事項の数が減り、結果から特定の設定/ポリシー行が削除されます。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>構成アナライザーの [構成の流れ分析と履歴] タブ

このタブでは、カスタム セキュリティ ポリシーに加えた変更を追跡できます。 既定では、次の情報が表示されます。

- **最終更新日時**
- **更新者**
- **設定名**
- **Policy**
- **型**

結果をフィルター処理するには、**[フィルター]** をクリックします。 表示される **フィルター** のフライアウトで、次のフィルターから選択できます。

- **開始時刻** と **終了時刻** (日付)
- **標準の保護** または **厳密な保護**

結果を .csv ファイルにエクスポートするには、[エクスポート] を **クリックします**。

![Configuration Analyzer の構成の流れ分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
