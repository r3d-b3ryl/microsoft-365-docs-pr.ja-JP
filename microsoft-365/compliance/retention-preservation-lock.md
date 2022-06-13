---
title: 保管ロックを使用して保持ポリシーへの変更を制限する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーと保持ラベル ポリシーとともに保管ロックを使用して、規制要件を満たし、不正な管理者から保護します。
ms.openlocfilehash: 228d4cd1a7778b5352df6d10d31b7e4c25af915f
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016286"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> [!IMPORTANT]
> 現在、[ アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention) で保持ロックはサポートされていません。

保管ロックは、アイテム保持ポリシーまたは保持ラベル ポリシーをロックして、グローバル管理者を含む誰もがポリシーをオフにしたり、ポリシーを削除したり、制限を緩和したりできないようにします。 この構成は、規制要件のために必要になる場合があります。また、不正な管理者からの保護に役立ちます。

保持ポリシーがロックされている場合:

- ポリシーを無効にしたり削除したりすることはできません
- 場所は追加できますが、削除できません
- 保持期間を延長することはできますが、短縮することはできません

保持ラベル ポリシーがロックされている場合:

- ポリシーを無効にしたり削除したりすることはできません
- 場所は追加できますが、削除できません
- ラベルは追加できますが、削除できません

つまり、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。

> [!IMPORTANT]
> アイテム保持ポリシーまたは保持ラベル ポリシーをロックする前に、その影響を理解し、それが組織に必要であるかどうかを確認することが非常に重要です。 たとえば、規制要件を満たす必要がある場合があります。 保管ロックを適用すると、管理者はこれらのポリシーを無効にすることも削除することもできなくなります。

[アイテムを規制レコードとしてマーク](records-management.md#records)するラベルのみが含まれる[公開](create-apply-retention-labels.md)したアイテム保持ラベル ポリシーか、[アイテム保持ポリシー](create-retention-policies.md)の作成後に保管ロックを構成します。

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>アイテム保持ポリシーまたは保持ラベル ポリシーをロックする方法

保管ロックを使用する必要がある場合は、PowerShell を使用する必要があります。 管理者は、保管ロックが適用された後に保持に関するポリシーを無効にしたり、削除したりすることができないため、この機能の有効化は、偶発的な構成を予防するものとして UI で使用することはできません。

保持ロックのいかなる構成にも対応するすべてのアイテム保持ポリシー。 保持ラベル ポリシーに保管ロックを適用するには、アイテムを規制レコードとしてマークするラベルのみがそれに含まれる必要があります。

1. [セキュリティ/コンプライアンス PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy) を実行してロックするポリシーの名前を検索します。例えば:
    
   ![PowerShell のアイテム保持ポリシーの一覧。](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. ポリシーに保管ロックを設定するには、ポリシーの名前を指定して [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) コマンドレットを実行し、*RestrictiveRetention* パラメーターを true に設定します。
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" -RestrictiveRetention $true
    ```
    
    例:
    
    ![PowerShell の RestrictiveRetention パラメーター。](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     メッセージが表示されたら、この構成に含まれる制限事項を読んで確認し、**Y** を選びます。
    
   ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

アイテム保持ポリシーに保管ロックが設定されました。 確認するには、`Get-RetentionCompliancePolicy` をもう一度実行しますが、ポリシーの名前を指定してポリシー パラメーターを表示します。

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

**RestrictiveRetention** が **True** に設定されていることを確認する必要があります。

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー。](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>関連項目

[データ ライフサイクル管理およびレコード管理の規制要件を満たすために役立つリソース](retention-regulatory-requirements.md)
