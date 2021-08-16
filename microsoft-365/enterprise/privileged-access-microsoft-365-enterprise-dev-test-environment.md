---
title: エンタープライズ テスト環境向けMicrosoft 365アクセス管理
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
description: このテスト ラボ ガイドを使用して、エンタープライズ テスト環境に対する権限Microsoft 365アクセス管理を有効にしてください。
ms.openlocfilehash: 9599048ae7ed4f4b3627da15d22d00e795bf28fc
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58250786"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境向けMicrosoft 365アクセス管理

*このテスト ラボ ガイドは、エンタープライズ環境とテスト環境Microsoft 365両方Office 365 Enterprise使用できます。*

この記事では、エンタープライズ テスト環境のセキュリティを強化するために特権アクセス管理を構成するMicrosoft 365説明します。

特権アクセス管理を構成するには、次の 3 つのフェーズが必要です。

- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 特権アクセス管理を構成する](#phase-2-configure-privileged-access-management)
- [フェーズ 3: 昇格されたタスクと特権タスクに承認が必要な場合の確認](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小限の要件で特権アクセス管理を軽量な方法で構成する場合は、「Lightweight base [configuration」の手順に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。
  
>[!NOTE]
>特権アクセス管理のテストでは、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 ここでは、特権アクセス管理をテストし、一般的な組織を表す環境でテストを行うオプションとして提供されています。

## <a name="phase-2-configure-privileged-access-management"></a>フェーズ 2: 特権アクセス管理を構成する

このフェーズでは、承認者グループを構成し、エンタープライズ テスト環境に対して、Microsoft 365アクセス管理を有効にしてください。 特権アクセス管理の詳細と概要については [、「Privileged access management」を参照してください](../compliance/privileged-access-management-overview.md)。

組織で特権アクセスを設定して使用するには、次の手順を実行します。

#### <a name="step-1-create-an-approvers-group"></a>[手順 1: 承認者のグループを作成する](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

特権アクセスの使用を開始する前に、管理者特権タスクおよび特権タスクへのアクセスに対する受信要求に対する承認権限を持つユーザーを決定します。 承認者グループに参加しているすべてのユーザーは、アクセス要求を承認できます。 特権アクセスを使用するには、メールが有効なセキュリティ グループをユーザーに作成Microsoft 365。 テスト環境で、新しいセキュリティ グループに "Privileged Access Approvers" という名前を付け、以前のテスト ラボ ガイドの手順で作成した "User 3" を追加します。

#### <a name="step-2-enable-privileged-access"></a>[手順 2: 特権アクセスを有効にする](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

既定の承認者グループを使用して Microsoft 365 で特権アクセスを明示的に有効にし、特権アクセス管理アクセス制御から除外する一連のシステム アカウントを含める必要があります。 このガイドのフェーズ 3 を開始する前に、組織で特権アクセスを有効にしてください。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>フェーズ 3: 昇格されたタスクと特権タスクに承認が必要な場合の確認

このフェーズでは、特権アクセス ポリシーが機能し、ユーザーが定義済みの管理者特権タスクおよび特権タスクを実行するために承認を必要とします。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義されていないタスクを実行する機能をテストする

まず、テスト環境で Exchange 役割管理役割を使用して構成されたユーザーの資格情報を使用して Exchange Management PowerShell に接続し、新しいジャーナル ルールの作成を試みる。 [New-JournalRule タスク](/powershell/module/exchange/new-journalrule)は現在、組織の特権アクセス ポリシーで定義されていません。

1. ローカル コンピューターで、テスト環境の Exchange 役割管理役割を持つ資格情報を使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート  >  **PowerShell** モジュールを開いてサインインします。
2. [Exchange PowerShell] で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

3. 新しいジャーナル ルールが管理 PowerShell で正常にExchange表示します。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>タスクの新しい特権アクセス ポリシーをNew-JournalRuleする

>[!NOTE]
>このガイドのフェーズ 2 の手順 1 と 2 をまだ完了していない場合は、テスト環境で特権アクセスを有効にするには、必ず手順に従って、"Privilege Access Approvers" という名前の承認者のグループを作成してください。

1. テスト環境の[[Microsoft 365 管理センター](https://admin.microsoft.com)管理] 役割を持つ資格情報Exchangeを使用して、ユーザーにサインインします。
2. 管理センターで、[セキュリティ]設定  >  **アクセス&**  >  **に移動します**。
3. [ **アクセス ポリシーと要求の管理] を選択します**。
4. [ポリシー **の構成] を選択** し、[ポリシーの **追加] を選択します**。
5. ドロップダウン フィールドから、次の値を選択または入力します。

    **ポリシーの種類**: タスク **ポリシー** スコープ : Exchange ポリシー名 **:** 新しいジャーナル ルール **承認の** 種類 : 手動 **承認** グループ : 特権アクセス承認者  

6. **[作成]** を選択してから、**[閉じる]** を選択します。 ポリシーが完全に構成され、有効になるには数分かかる場合があります。 次の手順で承認要件をテストする前に、ポリシーが完全に有効になる時間を許可してください。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特権アクセス ポリシーで定義New-JournalRuleタスクの承認要件をテストする

1. ローカル コンピューターで、テスト環境の Exchange 役割管理役割を持つ資格情報を使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート  >  **PowerShell** モジュールを開いてサインインします。

2. [Exchange PowerShell] で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 管理 PowerShell の "アクセス許可不足" エラー Exchange表示します。

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>タスクを使用して新しいジャーナル ルールを作成するアクセスNew-JournalRuleする

1. テスト環境の[[Microsoft 365 管理センター](https://admin.microsoft.com)管理] 役割を持つ資格情報Exchangeを使用して、ユーザーにサインインします。

2. 管理センターで、[セキュリティ]設定  >  **アクセス&**  >  **に移動します**。

3. [ **アクセス ポリシーと要求の管理] を選択します**。

4. [新 **しい要求] を選択します**。 ドロップダウン フィールドから、組織に適した値を選択します。

    **要求の** 種類 : タスク要求 **の** 範囲 : Exchange 要求 **:** 新しいジャーナル ルール期間 (時間 **)**: 2 **コメント**: 新しいジャーナル ルールを作成する要求のアクセス許可  

5. [保存 **] を** 選択し、[閉じる] **を選択します**。 要求はメールで承認者のグループに送信されます。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>新しいジャーナル ルールの作成に関する特権アクセス要求を承認する

1. テスト環境のユーザー 3[の](https://admin.microsoft.com)資格情報 (テスト環境の "特権アクセス承認者" セキュリティ グループのメンバー) を使用して、Microsoft 365 管理センターにサインインします。

2. 管理センターで、[セキュリティ]設定  >  **アクセス&**  >  **に移動します**。

3. [ **アクセス ポリシーと要求の管理] を選択します**。

4. 保留中の要求を選択し、[承認] **を選択して** ユーザー アカウントへのアクセスを許可して新しいジャーナル ルールを作成します。 アカウント (要求するユーザー) は、承認が許可されたという電子メールの確認を受け取る。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>タスクに対して承認された特権アクセスを持つ新しいジャーナル ルールの作成New-JournalRuleする

1. ローカル コンピューターで、テスト環境の Exchange 役割管理役割を持つ資格情報を使用して **、Microsoft Corporation** Microsoft Exchange Online リモート PowerShell モジュールの Exchange Online リモート  >  **PowerShell** モジュールを開いてサインインします。

2. [Exchange PowerShell] で、組織の新しいジャーナル ルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. 新しいジャーナル ルールが管理 PowerShell で正常にExchange表示します。

## <a name="next-step"></a>次の手順

テスト環境 [の追加情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
- [Microsoft 365 for enterprise の概要](microsoft-365-overview.md)
- [Microsoft 365 for enterprise のドキュメント](/microsoft-365-enterprise/)
