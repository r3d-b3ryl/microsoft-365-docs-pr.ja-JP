---
title: エンタープライズ テスト環境のMicrosoft 365の特権アクセス管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: scotv
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境のMicrosoft 365の特権アクセス管理を有効にします。
ms.openlocfilehash: 0c92cbd398e4c388fe3c5999c5e0aa9973c4ee06
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092097"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365の特権アクセス管理

*このテスト ラボ ガイドは、エンタープライズ環境とOffice 365 Enterpriseテスト環境の両方のMicrosoft 365に使用できます。*

この記事では、エンタープライズ テスト環境のMicrosoft 365のセキュリティを強化するために特権アクセス管理を構成する方法について説明します。

特権アクセス管理の構成には、次の 3 つのフェーズがあります。

- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 特権アクセス管理を構成する](#phase-2-configure-privileged-access-management)
- [フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要であることを確認する](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小限の要件を持つ軽量な方法で特権アクセス管理を構成する場合は、「 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
>[!NOTE]
>特権アクセス管理のテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services フォレストのディレクトリ同期が含まれます。 ここでは、特権アクセス管理をテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。

## <a name="phase-2-configure-privileged-access-management"></a>フェーズ 2: 特権アクセス管理を構成する

このフェーズでは、承認者グループを構成し、エンタープライズ テスト環境のMicrosoft 365の特権アクセス管理を有効にします。 特権アクセス管理の詳細と概要については、 [特権アクセス管理に関するページを](../compliance/privileged-access-management-overview.md)参照してください。

組織内で特権アクセスを設定して使用するには、次の手順を実行します。

#### <a name="step-1-create-an-approvers-group"></a>[手順 1: 承認者のグループを作成する](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

特権アクセスの使用を開始する前に、昇格されたタスクと特権のあるタスクへのアクセスに対する受信要求に対する承認機関を持つユーザーを決定します。 承認者のグループに属するすべてのユーザーは、アクセス要求を承認できます。 特権アクセスを使用するには、Microsoft 365にメールが有効なセキュリティ グループを作成する必要があります。 テスト環境で、新しいセキュリティ グループに "Privileged Access Approvers" という名前を付け、前のテスト ラボ ガイドの手順で以前に作成した "ユーザー 3" を追加します。

#### <a name="step-2-enable-privileged-access"></a>[手順 2: 特権アクセスを有効にする](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

既定の承認者グループを持つMicrosoft 365で特権アクセスを明示的に有効にする必要があり、特権アクセス管理アクセス制御から除外するシステム アカウントのセットを含める必要があります。 このガイドのフェーズ 3 を開始する前に、必ず組織内で特権アクセスを有効にしてください。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>フェーズ 3: 昇格されたタスクと特権を持つタスクに承認が必要であることを確認する

このフェーズでは、特権アクセス ポリシーが機能していること、およびユーザーが定義済みの昇格済みタスクと特権タスクを実行するための承認が必要であることを確認します。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義されていないタスクを実行する機能をテストする

まず、テスト環境で Exchange ロール管理ロールを使用して構成されたユーザーの資格情報を使用して Exchange Management PowerShell に接続し、新しい履歴ルールの作成を試みます。 [New-JournalRule](/powershell/module/exchange/new-journalrule) タスクは、現在、組織の特権アクセス ポリシーで定義されていません。

1. ローカル コンピューターで、テスト環境の Exchange ロール管理ロールを持つ資格情報を使用して、**Microsoft Corporation** >  **のExchange Online Remote PowerShell モジュールMicrosoft Exchange Onlineリモート PowerShell モジュール** を開いてサインインします。
2. Exchange管理 PowerShell で、組織の新しい履歴ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

3. 新しい履歴ルールが Exchange Management PowerShell で正常に作成されたことを確認します。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>New-JournalRule タスクの新しい特権アクセス ポリシーを作成する

>[!NOTE]
>このガイドのフェーズ 2 の手順 1 と手順 2 をまだ完了していない場合は、テスト環境で特権アクセスを有効にする "Privilege Access Approvers" という名前の承認者のグループを作成する手順に従ってください。

1. テスト環境の[Exchange](https://admin.microsoft.com) ロール管理ロールで資格情報を使用して、Microsoft 365 管理センターにサインインします。
2. 管理センターで、**設定****Security &** >  **PrivacyPrivileged** >  アクセスに移動します。
3. [ **アクセス ポリシーと要求の管理**] を選択します。
4. [ **ポリシーの構成]** を選択し、[ **ポリシーの追加]** を選択します。
5. ドロップダウン フィールドから、次の値を選択または入力します。

    **ポリシーの種類**: タスク **ポリシースコープ**: Exchange **Policy name**: New Journal Rule **Approval type**: Manual **Approval group**: Privileged Access Approvers  

6. **[作成]** を選択してから、**[閉じる]** を選択します。 ポリシーが完全に構成されて有効になるまで数分かかる場合があります。 次の手順で承認要件をテストする前に、ポリシーが完全に有効になる時間を確保してください。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義されたNew-JournalRule タスクの承認要件をテストする

1. ローカル コンピューターで、テスト環境の Exchange ロール管理ロールを持つ資格情報を使用して、**Microsoft Corporation** >  **のExchange Online Remote PowerShell モジュールMicrosoft Exchange Onlineリモート PowerShell モジュール** を開いてサインインします。

2. Exchange管理 PowerShell で、組織の新しい履歴ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exchange Management PowerShell で "アクセス許可が不十分" というエラーを表示します。

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>New-JournalRule タスクを使用して新しい履歴ルールを作成するためのアクセスを要求する

1. テスト環境の[Exchange](https://admin.microsoft.com) ロール管理ロールで資格情報を使用して、Microsoft 365 管理センターにサインインします。

2. 管理センターで、**設定****Security &** >  **PrivacyPrivileged** >  アクセスに移動します。

3. [ **アクセス ポリシーと要求の管理**] を選択します。

4. [ **新しい要求]** を選択します。 ドロップダウン フィールドから、組織に適した値を選択します。

    **要求の種類**: タスク **要求スコープ**: Exchange **Request for**: New Journal Rule **Duration (時間)**: 2 **コメント**: 新しいジャーナル ルールを作成するための要求アクセス許可  

5. **[保存] を** 選択し、[**閉じる**] を選択します。 要求は、電子メールで承認者のグループに送信されます。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>新しいジャーナル ルールの作成に対する特権アクセス要求を承認する

1. テスト環境のユーザー 3 の資格情報 (テスト環境の "Privileged Access Approvers" セキュリティ グループのメンバー) [を使用して](https://admin.microsoft.com)、Microsoft 365 管理センターにサインインします。

2. 管理センターで、**設定****Security &** >  **PrivacyPrivileged** >  アクセスに移動します。

3. [ **アクセス ポリシーと要求の管理**] を選択します。

4. 保留中の要求を選択し、[ **承認** ] を選択してユーザー アカウントへのアクセスを許可し、新しい履歴ルールを作成します。 アカウント (要求しているユーザー) には、承認が付与されたことを示す電子メールの確認が届きます。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>New-JournalRule タスクに対して承認された特権アクセスを持つ新しい履歴ルールの作成をテストする

1. ローカル コンピューターで、テスト環境の Exchange ロール管理ロールを持つ資格情報を使用して、**Microsoft Corporation** >  **のExchange Online Remote PowerShell モジュールMicrosoft Exchange Onlineリモート PowerShell モジュール** を開いてサインインします。

2. Exchange管理 PowerShell で、組織の新しい履歴ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 新しい履歴ルールが Exchange Management PowerShell で正常に作成されたことを確認します。

## <a name="next-step"></a>次の手順

テスト環境の [追加情報保護機能](m365-enterprise-test-lab-guides.md#information-protection) と機能について説明します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
- [Microsoft 365 for enterprise の概要](microsoft-365-overview.md)
- [Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
