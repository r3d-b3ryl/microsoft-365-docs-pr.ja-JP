---
title: エンタープライズ向け Microsoft 365 テスト環境の特権アクセス管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: このテスト ラボ ガイドを使用して、エンタープライズ 向け Microsoft 365 テスト環境で特権アクセス管理を有効にしてください。
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126419"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ向け Microsoft 365 テスト環境の特権アクセス管理

*このテスト ラボ ガイドは、Microsoft 365 for enterprise と Office 365 Enterprise テスト環境の両方に使用できます。*

この記事では、エンタープライズ 向け Microsoft 365 テスト環境のセキュリティを強化するために特権アクセス管理を構成する方法について説明します。

権限を持つアクセス管理を構成するには、次の 3 つのフェーズが必要です。
- [フェーズ 1: エンタープライズ向け Microsoft 365 テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 特権アクセス管理を構成する](#phase-2-configure-privileged-access-management)
- [フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要な状態を確認する](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ向け Microsoft 365 のテスト ラボ ガイド スタックのすべての記事のビジュアル マップについては [、Microsoft 365 enterprise テスト](../downloads/Microsoft365EnterpriseTLGStack.pdf)ラボ ガイド スタックにアクセスしてください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ向け Microsoft 365 テスト環境を構築する

最小要件で特権アクセス管理を軽量な方法で構成する場合は、「ライトウェイト基本構成」の手順 [に従ってください](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。
  
>[!NOTE]
>特権アクセス管理をテストする場合、シミュレーションのエンタープライズ テスト環境は必要とされません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメイン サービス フォレストのディレクトリ同期が含まれます。 ここでは、特権アクセス管理をテストし、一般的な組織を表す環境で試用できるよう、オプションとして提供されています。

## <a name="phase-2-configure-privileged-access-management"></a>フェーズ 2: 特権アクセス管理を構成する

このフェーズでは、承認者グループを構成し、エンタープライズ テスト環境用に Microsoft 365 の特権アクセス管理を有効にしてください。 特権アクセス管理の詳細と概要については、「特権アクセス管理」 [を参照してください](../compliance/privileged-access-management-overview.md)。

組織で特権アクセスをセットアップして使用するには、次の手順を実行します。

#### <a name="step-1-create-an-approvers-group"></a>[手順 1: 承認者のグループを作成する](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

特権アクセスの使用を開始する前に、管理者特権タスクおよび特権タスクへのアクセス要求を受信する承認機関を持つユーザーを決定します。 承認者のグループに含めるすべてのユーザーは、アクセス要求を承認できます。 特権アクセスを使用するには、Microsoft 365 でメールが有効なセキュリティ グループを作成する必要があります。 テスト環境で、新しいセキュリティ グループに「Privileged Access Approvers」という名前を付け、以前のテスト ラボ ガイドの手順で作成した "User 3" を追加します。

#### <a name="step-2-enable-privileged-access"></a>[手順 2: 特権アクセスを有効にする](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

既定の承認者グループを使用して Microsoft 365 で特権アクセスを明示的に有効にし、特権アクセス管理アクセス制御から除外する一連のシステム アカウントを含める必要があります。 このガイドのフェーズ 3 を開始する前に、組織で特権アクセスを有効にしてください。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要な状態を確認する

このフェーズでは、特権アクセス ポリシーが機能し、ユーザーが定義済みの昇格されたタスクと特権タスクを実行するために承認を必要とします。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義されていないタスクを実行する機能をテストする

まず、テスト環境でグローバル管理者として構成されたユーザーの資格情報を使用して Exchange Management PowerShell に接続し、新しいジャーナル ルールの作成を試みる。 [New-JournalRule](/powershell/module/exchange/new-journalrule)タスクは、現在、組織の特権アクセス ポリシーで定義されていません。

1. ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いて  >  サインインします。

1. Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. 新しいジャーナル ルールが Exchange Management PowerShell で正常に作成されたことを確認します。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>タスクの新しい特権アクセス ポリシーをNew-JournalRuleする

>[!NOTE]
>このガイドのフェーズ 2 の手順 1 と 2 をまだ完了していない場合は、テスト環境で特権アクセスを有効にする "Privilege Access Approvers" という名前の承認者のグループを作成する手順に従ってください。

1. テスト環境のグローバル管理者アカウントの資格情報を使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [ポリシー **の構成] を選択し**、[ポリシーの **追加] を選択します**。

5. ドロップダウン フィールドで、次の値を選択または入力します。

    **ポリシーの種類**: タスク

    **ポリシースコープ**: 交換

    **ポリシー名**: 新しいジャーナル ルール

    **承認の種類**: 手動

    **承認グループ**: 特権アクセス承認者

6. **[作成]** を選択してから、**[閉じる]** を選択します。 ポリシーが完全に構成され、有効になるには数分かかる場合があります。 次の手順で承認要件をテストする前に、ポリシーが完全に有効になる時間を許可してください。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義New-JournalRuleタスクのテスト承認要件

1. ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いてサインイン  >  します。

2. Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exchange Management PowerShell で "十分なアクセス許可が不足しています" というエラーを表示します。

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>タスクを使用して新しいジャーナル ルールを作成するアクセスNew-JournalRuleする

1. テスト環境のグローバル管理者アカウントを使用して [、Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします。

2. In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. [新 **しい要求] を選択します**。 ドロップダウン フィールドから、組織に適した値を選択します。

    **要求の種類**: タスク

    **要求スコープ**: 交換

    **要求:** 新しいジャーナル ルール

    **期間 (時間)**: 2

    **コメント**: 新しいジャーナル ルールを作成するためのアクセス許可を要求する

5. [保存 **] を** 選択し、[閉じる] を **選択します**。 要求は、承認者のグループに電子メールで送信されます。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>新しいジャーナル ルールを作成する特権アクセス要求を承認する

1. テスト環境で User 3 の資格情報を使用して [Microsoft 365](https://admin.microsoft.com) 管理センターにサインインします (テスト環境の "Privileged Access Approvers" セキュリティ グループのメンバー)。

2. In the Admin Center, go to **Settings**  >  **Security & Privacy**  >  **Privileged access**.

3. [アクセス **ポリシーと要求の管理] を選択します**。

4. 保留中の要求を選択し、[承認]を選択してグローバル管理者アカウントへのアクセス権を付与し、新しいジャーナル ルールを作成します。 グローバル管理者アカウント (要求ユーザー) は、承認が許可されたという確認メールを受信します。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>タスクに対して承認された特権アクセスを持つ新しいジャーナル ルールNew-JournalRuleテストする

1. ローカル コンピューターで、テスト環境のグローバル管理者アカウントを使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート PowerShell モジュールを開いて  >  サインインします。

1. Exchange Management PowerShell で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. 新しいジャーナル ルールが Exchange Management PowerShell で正常に作成されたことを確認します。

## <a name="next-step"></a>次の手順

テスト環境 [のその他の](m365-enterprise-test-lab-guides.md#information-protection) 情報保護機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
