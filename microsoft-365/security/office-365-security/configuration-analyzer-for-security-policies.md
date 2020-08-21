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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準保護と制限保護のプレセット セキュリティ ポリシーの下の設定を含むセキュリティ ポリシーを検索して修正する方法について学習できます。
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825775"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>EOP と Office 365 ATP の保護ポリシー Officeの構成アナライザー

> [!NOTE]
> このトピックで説明する機能はプレビューであり、すべての組織で利用できるものであり、変更される可能性があります。

セキュリティ & コンプライアンス センターの Configuration Analyzer では、事前設定されたセキュリティ ポリシーの標準保護と制限保護のプロファイル設定の下に表示される設定を含むセキュリティ ポリシーを一元的に [検索して修正できます](preset-security-policies.md)。

構成アナライザーでは、以下の種類のポリシーが分析されます。

- **Exchange Online Protection (EOP) ポリシー**: これには、Exchange Online メールボックスを使用している Microsoft 365 組織と Exchange Online メールボックスを持つスタンドアロン EOP 組織が含まれます。
  
  - [スパム対策ポリシー](configure-your-spam-filter-policies.md)。
  - [マルウェア対策ポリシー](configure-anti-malware-policies.md)。
  - [EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。

- **Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または Office 365 の ATP アドオン サブスクリプションを持つ組織が含まれます。

  - ATP フィッシング対策ポリシーには、以下が含まれます。

    - EOP フ [ィッシング](set-up-anti-phishing-policies.md#spoof-settings) 対策ポリシーで使用できるのと同じスプーフィング設定。
    - [偽装の設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高度なフィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [安全なリンクポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。

  - [安全な添付ファイル ポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。

基準 **として** 使用 **される標準および制限の** ポリシー設定値については、EOP と [Office 365 ATP セキュリティの推奨設定に説明されています](recommended-settings-for-eop-and-office365-atp.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 構成アナライザーページ **に直接移動するには** 、以下を使用します <https://protection.office.com/configurationAnalyzer> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 構成アナライザ **ーを** 使用してセキュリティ ポリシーを更新するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 構成アナライザーに対する読み取り専用アクセスを実行するには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>セキュリティ センターで構成アナライザー&使用する

セキュリティ/コンプライアンス センター&、脅威管理ポリシー **構成アナラ** \> **イザー** \> **に移動します**。

![[脅威管理ポリシー] ページの構成アナライザー \> ウィジェット](../../media/configuration-analyzer-widget.png)

構成アナライザーには 2 つの主なタブがあります。

- **[設定] と推奨**事項: [標準] または [制限する] を選択し、それらの設定を既存のセキュリティ ポリシーと比較します。 結果の中で、設定の値を調整して、標準または高クォータと同じレベルに設定できます。

- **構成重複分析と履歴**: このビューでは、構成アナライザーの結果に基づいてポリシーに加えた変更を一定期間で追跡できます。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>構成アナライザーの [設定とおすすめ] タブ

既定では、タブは標準保護プロファイルとの比較で開かれます。 [フィルターする] をクリックして、[高一次的な保護プロファイル] をクリック **して、[書き込み] をクリックします**。 標準的な推奨事項の表示 **を選択して、前に戻す必要があります**。

![構成アナライザーでの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

既定では、 **ポリシー グループ/設定名** の列には、異なる種類のセキュリティ ポリシーと、改善が必要なポリシーの設定の数 (存在する場合) が折りたたまれたビューに含まれます。 ポリシーの種類は次のとおりです。

- **スパム対策**
- **フィッシング対策**
- **マルウェア対策**
- **ATP の安全な添付ファイル** (サブスクリプションに ATP が含まれている場合)
- **ATP の安全なリンク** (サブスクリプションに ATP が含まれている場合)

既定のビューでは、すべてが折りたたされています。 各ポリシーの横に、ポリシーの比較結果の概要 (変更できます) と、標準または高レベルの保護プロファイル (変更することはできません) に対応するポリシーの設定が表示されます。 次の情報が表示されます。

- **緑 : 既存**のすべてのポリシーのすべての設定は、比較する保護プロファイル以上に安全です。
- **Amber**: 既存のポリシーの設定の数がわずかで、比較する保護プロファイルに安全でない。
- **Red**: 既存のポリシーの設定の数が大幅にセキュアになっていないのは、その相性が安全な保護プロファイルではありません。 これは、多くのポリシーの設定や、1 つのポリシー内の多くの設定にできます。

使い気に入りになっておりの比較を行う場合は、テキスト「すべての設定 **: 推奨事項」** \<**Standard** or **Strict**\> **が表示されます**。 そうしないと、変更する推奨設定の数が表示されます。

ポリシー グループ/ **設定の名前を展開すると**、注意を必要とするすべてのポリシーおよび関連する設定が表示されます。 または、特定の種類のポリシー (スパム対策など) **を拡張**して、ユーザーの注意を必要とするポリシーの種類の設定だけを表示することができます。

比較に推奨事項が (緑) されていない場合は、ポリシーを拡張するものは何もありません。 改善するいくつかの推奨事項 (amber または red) がある場合、注意が必要な設定がわかり、対応する情報は次の列に示されています。

- ユーザーの注意が必要な設定の名前。 たとえば、前のスクリーンショットでは、それはスパム対策ポリシー **のバルク** メールしきい値です。

- **Policy:** 設定を含む影響を受けるポリシーの名前。

- **適用:** 影響を受けるポリシーが適用されるユーザーの数。

- **現在の**構成 : 設定の現在の値。

- **最終更新**日: ポリシーが最後に変更された日付。

- **おす**すめ : 標準または [上書きの保護プロファイル] の設定値。 保護プロファイルの推奨値と一致するようにポリシーの設定の値を変更するには **、[Adopt] をクリックします**。 変更が成功すると、次のメッセージが表示されます: **おすすめは正しく導入されています**。 [ **更新]** をクリックすると、使用するおすすめ候トの数が減少し、特定の設定/ポリシー行が結果から削除されます。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>構成ダッシュ化と構成アナライザーの [履歴] タブ

このタブでは、セキュリティ アナライザーの情報に基づいて、カスタム セキュリティ ポリシーに加えた変更を追跡できます。 既定では、次の情報が表示されます。

- **最終更新日時**
- **更新者**
- **設定名**
- **ポリシー**
- **型**

結果をフィルター処理するには、**[フィルター]** をクリックします。 表示される **[フィルター** ] ポップアップでは、次のフィルターから選択できます。

- **開始時刻** と **終了時刻** (date)
- **標準的** な **保護または高い保護**

結果を .csv ファイルにエクスポートするには、[エクスポート] をクリック **します**。

![構成ダッシュの分析と Configuration Analyzer の履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
