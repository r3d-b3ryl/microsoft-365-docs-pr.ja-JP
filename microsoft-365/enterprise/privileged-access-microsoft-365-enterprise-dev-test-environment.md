---
title: Microsoft 365 Enterprise テスト環境の特権アクセスの管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: アクセス権限の管理を有効にするのに Microsoft 365 エンタープライズ テスト環境に対応するこのテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869007"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境の特権アクセスの管理

この資料の手順についてで Microsoft 365 エンタープライズ テスト環境でセキュリティを強化するのにはアクセス権限の管理を構成します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法でアクセス権限の管理を構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業内のアクセス権限の管理を構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> アクセス権限管理のテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。ここで提供されている、オプションとしてテストすることができるように権限のアクセス管理と一般的な組織を表す環境で実験します。 

## <a name="phase-2-configure-privileged-access-management"></a>フェーズ 2: アクセス権限の管理を構成します。

このフェーズでは、承認者グループの構成し、Microsoft 365 エンタープライズ テスト環境のアクセス権限の管理を有効にします。詳細および特権の概要の管理にアクセス、 [Office 365 にアクセス権限の管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)を参照してください。

設定し、Office 365 の組織内のアクセス権限を使用してこれらの手順に従います。

- [手順 1: 承認者のグループを作成します。](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    特権アクセスの使用を開始する前に、管理者特権、特権を持つタスクにアクセスするための着信方向の要求の承認権限を持ってことを確認します。承認者グループの一部になっているユーザーはアクセス権の要求を承認することになります。これは、Office 365 のメールが有効なセキュリティ グループを作成することによって有効になります。テスト環境で「特権を持つアクセスの承認」をという名前の新しいセキュリティ グループを作成し、、追加の"3" 以前のテスト ラボ ガイドの手順で作成済みのユーザーです。

- [手順 2: アクセス権限を有効にします。](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    アクセス権限を明示的にオンにする Office 365 の既定の承認者グループとアクセス権限の管理アクセスの制御から除外することがシステム アカウントのセットを含む必要があります。このガイドの第 3 段階を開始する前に Office 365 の組織内のアクセス権限を有効にすることを確認します。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>フェーズ 3: は、承認が昇格した特権と特権を持つタスクに必要であることを確認します。
このフェーズでは、アクセス権限ポリシーが機能して、そのユーザーが管理者特権、特権の定義済みのタスクを実行するために承認を必要とするを確認します。

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>特権のアクセス ポリシーで定義されていないタスクを実行する機能をテストします。

まず、テスト環境でグローバル ・ アドミニストレーターとして構成されたユーザーの資格情報を持つ Exchange 管理 PowerShell に接続し、新しいジャーナル ルールを作成しようとしてください。[新規 JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)タスクは、組織の管理者のアクセス ポリシーで現在定義されていません。

1. ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > **Microsoft Exchange Online リモート PowerShell モジュール**のグローバル管理を使用するが、テスト環境を考慮します。

2. Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. ジャーナル ルールの新規作成されたこと正常に Exchange 管理 PowerShell を表示します。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>新規 JournalRule タスク用の新しいアクセス権限ポリシーを作成します。

> [!NOTE]
> 手順 1 と 2 からは、このガイドの第 2 フェーズが完了していない場合、は、「特権のアクセスの承認」という名前の承認者のグループを作成して、テスト環境でのアクセス権限有効にする手順を必ず次にあります。

1. テスト環境のグローバル管理者アカウントに資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)に署名します。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. **ポリシーを構成する**を選択し、[**ポリシーの追加**] を選択します。

5. ドロップ ダウン フィールドから選択または次の値を入力してください。
    
    **ポリシーの種類**: タスク

    **ポリシーのスコープ**: Exchange

    **ポリシー名**: 新しいジャーナル ルール

    **承認タイプ**: 手動

    **承認グループ**: アクセスの権限を持つ承認者

6. **作成**し、[**閉じる**を選択します。ポリシーを完全に構成し、有効にするのには数分かかる場合があります。承認要件を次の手順でテストする前に完全に有効にするポリシーの時間を確保することを確認します。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特権のアクセス ポリシーで定義されている新しい JournalRule タスクの承認要件をテストします。

1. ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > テスト用アカウントの**Microsoft Exchange Online リモート PowerShell モジュール**を使用してグローバル管理者を使用して環境です。

2. Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Exchange 管理 PowerShell の"「アクセス許可不十分です。 のエラーをを参照してください。

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>新規 JournalRule タスクを使用して、新しいジャーナル ルールを作成するアクセス権の要求

1. テスト環境のグローバル管理者アカウントを使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. **新しい要求**を選択します。ドロップ ダウン フィールドから、組織の適切な値を選択します。

    **要求の種類**: タスク

    **要求スコープ**: Exchange

    **要求**: 新しいジャーナル ルール

    **期間 (時間)**: 2

    **コメント**: 新しいジャーナル ルールを作成するアクセス許可を要求します。

5. **保存**し、**閉じる**を選択します。要求は、電子メールでの承認者のグループに送信されます。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>新しいジャーナル ルールを作成するためのアクセス権限の要求を承認します。

1. ユーザー 3 のテスト環境 (テスト環境で"特権を持つアクセスを承認者] セキュリティ グループのメンバー) の資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。

2. **設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。

3. **アクセス ポリシーを管理し要求**を選択します。

4. 保留中の要求を選択し、[新しい仕訳ルールを作成するのにはグローバル管理者アカウントへのアクセスを許可する**承認**を選択します。承認が与えられていることを確認通知メールは、グローバル管理者アカウント (要求元のユーザー) に送信されます。  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>新規 JournalRule タスクの承認のアクセス権限を持つ新しいジャーナル ルールを作成するテスト

1. ローカル コンピューターを開き、サインインを Exchange オンライン リモート PowerShell モジュールでは、**米国 Microsoft Corporation** > **Microsoft Exchange Online リモート PowerShell モジュール**のグローバル管理を使用するが、テスト環境を考慮します。

2. Exchange 管理 Powershell では、組織の新しいジャーナル ルールを作成します。

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. ジャーナル ルールの新規作成されたこと正常に Exchange 管理 PowerShell を表示します。

## <a name="next-step"></a>次の手順

追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)