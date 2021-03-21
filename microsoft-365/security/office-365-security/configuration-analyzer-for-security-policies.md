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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準保護と厳密な保護の事前設定されたセキュリティ ポリシーの下にあるセキュリティ ポリシーを見つけて修正する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 49c54fa93d5ed95c6c3e0aa948646dd544ea4a5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924446"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP および Microsoft Defender の保護ポリシー用の構成アナライザー (Office 365)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

セキュリティ & コンプライアンス センターの構成アナライザーは、設定が事前設定されたセキュリティ ポリシーの標準保護および厳密な保護プロファイル設定の下にあるセキュリティ ポリシーを見つけて修正するための中心的な場所を [提供します](preset-security-policies.md)。

次の種類のポリシーは、構成アナライザーによって分析されます。

- **Exchange Online Protection (EOP)** ポリシー : これには、Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロン EOP 組織が含まれます。

  - [スパム対策ポリシー](configure-your-spam-filter-policies.md)。
  - [マルウェア対策ポリシー](configure-anti-malware-policies.md)。
  - [EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。

- **Microsoft Defender for Office 365** ポリシー: これには、Microsoft 365 E5 または Defender が 365 アドオン サブスクリプションの組織Office含まれます。

  - Microsoft Defender for Office 365 のフィッシング対策ポリシー。

    - EOP [フィッシング対策](set-up-anti-phishing-policies.md#spoof-settings) ポリシーで使用できるスプーフィング設定と同じです。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [高度なフィッシングのしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [セーフ リンク ポリシー](set-up-atp-safe-links-policies.md)。

  - [安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)。

基準 **として使用** される Standard および **Strict** ポリシー設定の値については、「EOP および Microsoft Defender for Office [365 セキュリティの推奨設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [構成アナライザー] ページに直接 **移動するには、** を使用します <https://protection.office.com/configurationAnalyzer> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:
  - 構成アナライザーを使用してセキュリティ ポリシーを更新するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。
  - 構成アナライザーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループ **のメンバーである** 必要があります。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  > [!NOTE]
  >  
  > - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターの構成&使用する

セキュリティ 管理コンプライアンス センター&、脅威管理 **ポリシー** \> **構成アナライザーに** \> **移動します**。

![[脅威管理ポリシー] ページの構成 \> アナライザー ウィジェット](../../media/configuration-analyzer-widget.png)

構成アナライザーには、次の 2 つの主なタブがあります。

- **設定と推奨事項**: [標準] または [厳密] を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。 結果では、設定の値を調整して、Standard または Strict と同じレベルに設定できます。

- **構成ドリフトの分析と履歴**: このビューでは、時間の流れによってポリシーの変更を追跡できます。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>構成アナライザーの [設定と推奨事項] タブ

既定では、標準保護プロファイルとの比較でタブが開きます。 [厳密な推奨事項の表示] をクリックすると、厳密な保護プロファイルの **比較に切り替えます**。 切り替えるには、[標準の **推奨事項の表示] を選択します**。

![構成アナライザーの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

既定では、[ **ポリシー グループ/** 設定名] 列には、さまざまな種類のセキュリティ ポリシーの折りたたまれているビューと、改善が必要な設定の数 (必要な場合) が含まれる。 ポリシーの種類は次のとおりです。

- **スパム対策**
- **フィッシング対策**
- **マルウェア対策**
- **ATP の安全な添付** ファイル (サブスクリプションに Microsoft Defender for Office 365)
- **ATP セーフ リンク** (サブスクリプションに Microsoft Defender for Office 365)

既定のビューでは、すべてが折りたためます。 各ポリシーの横には、ポリシー (変更できる) と、Standard または Strict Protection プロファイルの対応するポリシー (変更できない) の設定の比較結果の概要があります。 比較している保護プロファイルに関する次の情報が表示されます。

- **緑**: すべての既存のポリシーのすべての設定は、少なくとも保護プロファイルと同じ安全です。
- **オレンジ**: 既存のポリシーの設定の数が少ない場合、保護プロファイルほど安全ではありません。
- **赤**: 既存のポリシーの設定のかなりの数は、保護プロファイルほど安全ではありません。 これは、多くのポリシーのいくつかの設定、または 1 つのポリシーの多くの設定である可能性があります。

良好な比較を行う場合は、「すべての設定は推奨事項に従う」 **というテキスト** \<**Standard** or **Strict**\> **が表示されます**。 それ以外の場合は、変更する推奨設定の数が表示されます。

[ポリシー グループ **/設定** 名] を展開すると、注意が必要な各ポリシーのすべてのポリシーと関連付けられた設定が表示されます。 または、特定の種類のポリシー (スパム **対策など)** を展開して、注意が必要なポリシーの種類に設定を表示することもできます。

比較に改善の推奨事項がない場合 (緑)、ポリシーを展開すると何も表示しません。 改善に関する推奨事項 (オレンジまたは赤) が多数ある場合は、注意が必要な設定が表示され、対応する情報が次の列に表示されます。

- 注意が必要な設定の名前。 たとえば、前のスクリーンショットでは、スパム **対策ポリシーの** バルク メールしきい値です。

- **ポリシー**: 設定を含む影響を受けるポリシーの名前。

- **適用:** 影響を受けるポリシーが適用されるユーザーの数。

- **現在の構成**: 設定の現在の値。

- **最終更新日 :** ポリシーが最後に変更された日付。

- **推奨事項**: Standard または Strict Protection プロファイルの設定の値。 ポリシーの設定の値を保護プロファイルの推奨値と一致する値に変更するには、[採用] を **クリックします**。 変更が成功した場合は、「推奨事項が正常に採用されました」 **というメッセージが表示されます**。 [ **最新の情報** に更新] をクリックすると、推奨事項の数が減り、結果から特定の設定/ポリシー行が削除されます。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>構成アナライザーの [構成ドリフト分析と履歴] タブ

このタブでは、カスタム セキュリティ ポリシーに加えた変更を追跡できます。 既定では、次の情報が表示されます。

- **最終更新日時**
- **変更者**
- **設定名**
- **Policy**
- **型**

結果をフィルター処理するには、**[フィルター]** をクリックします。 表示される **[フィルター** ] フライアウトで、次のフィルターから選択できます。

- **開始時刻** と **終了時刻** (日付)
- **標準保護または****厳密な保護**

結果を .csv ファイルにエクスポートするには、[エクスポート] を **クリックします**。

![Configuration Analyzer の構成ドリフト分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)