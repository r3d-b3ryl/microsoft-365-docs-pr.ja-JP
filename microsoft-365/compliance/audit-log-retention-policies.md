---
title: 監査ログの保持ポリシーを管理する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。 監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。
ms.openlocfilehash: c2449ab90d04fd44909999d25b940ee4d2758b15
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753336"
---
# <a name="manage-audit-log-retention-policies"></a>監査ログの保持ポリシーを管理する

セキュリティ/コンプライアンス センターで監査ログの保持ポリシーを作成および管理できます。 監査ログの保持ポリシーは、Microsoft 365 の新しい高度な監査機能の一部です。 監査ログの保持ポリシーでは、組織の監査ログを保持する期間を指定できます。 監査ログは、最大 10 年間保持できます。 次の条件を基にしてポリシーを作成できます。

- 1 つまたは複数の Microsoft 365 サービスのすべてのアクティビティ

- すべてのユーザーまたは特定のユーザーによって実行された (Microsoft 365 サービス内の) 特定のアクティビティ

- 優先度レベルは、組織内に複数のポリシーがある場合に、どのポリシーが優先されるかを指定する

## <a name="default-audit-log-retention-policy"></a>既定の監査ログの保持ポリシー

Microsoft 365 の高度な監査には、すべての組織の既定の監査ログの保持ポリシーが用意されています。 このポリシーでは、Exchange、SharePoint、および Azure Active Directory の監査レコードを 1 年間保持します。 この既定のポリシーは、 **ワークロード** プロパティ (アクティビティが発生したサービス) の **AzureActiveDirectory** 、 **Exchange** 、または **SharePoint** の値を含む監査レコードを保持します。 既定のポリシーは変更できません。 既定のポリシーに含まれている各ワークロードのレコード種類の一覧については、この記事の「[詳細情報](#more-information)」を参照してください。

> [!NOTE]
> 既定の監査ログの保持ポリシーは、Office 365 または Microsoft 365 E5 ライセンスが割り当てられているユーザー、または Microsoft 365 E5 コンプライアンスまたは Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスを持つユーザーが実行したアクティビティの監査レコードにのみ適用されます。 組織に E5 以外のユーザーがいる場合、対応する監査レコードは 90 日間保持されます。

## <a name="before-you-create-an-audit-log-retention-policy"></a>監査ログの保持ポリシーを作成する前に

- 監査保持ポリシーを作成または変更するには、セキュリティ/コンプライアンス センターの組織構成の役割を割り当てる必要があります。

- 組織では、最大 50 個の監査ログの保持ポリシーを設定できます。

- 監査ログを 90 日以上保持するには、監査ログを生成したユーザーに Office 365 E5 または Microsoft 365 E5 ライセンスを割り当てるか、または Microsoft 365 E5 Compliance または E5 eDiscovery および監査アドオン ライセンスが必要です。

- 組織によって作成されるすべてのカスタム監査ログの保持ポリシーは、既定の保持ポリシーよりも優先されます。 たとえば、保持期間が 1 年未満の Exchange メールボックス アクティビティに対して監査ログの保持ポリシーを作成すると、Exchange メールボックス アクティビティの監査レコードは、カスタム ポリシーで指定されている短い期間保持されます。

## <a name="create-an-audit-log-retention-policy-in-the-compliance-center"></a>コンプライアンス センターで監査ログの保持ポリシーを作成します。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) に移動し、セキュリティ/コンプライアンス センターで組織構成の役割が割り当てられているユーザー アカウントでサインインします。

2. Microsoft 365 コンプライアンス センターの左側のウィンドウで、[ **すべてを表示** ] をクリックし、[ **監査** ] をクリックします。

    [ **監査** ] ページが表示されます。

    ![コンプライアンス センターの監査ログの検索ページ](../media/AuditLogRetentionPolicy1.png)

3. [ **監査保持ポリシーの作成** ] をクリックし、ポップアップ ページの次のフィールドに入力します。

    ![監査保持ポリシーのポップアップ ページ](../media/AuditLogRetentionPolicy2.png)

   1. **名前:** 監査ログの保持ポリシーの名前です。 この名前は組織で固有である必要があります。

   2. **説明:** 省略可能ですが、レコードの種類やワークロード、ポリシーで指定されたユーザー、期間など、ポリシーに関する情報を提供するのに役立ちます。

   3. **ユーザー:** ポリシーを適用する 1 人以上のユーザーを選択します。 このボックスを空白のままにすると、ポリシーがすべてのユーザーに適用されます。 **レコードの種類** を空白のままにする場合は、ユーザーを選択する必要があります。

   4. **レコードの種類:** ポリシーの適用対象となる監査レコードの種類です。 このプロパティを空白のままにする場合は、[ **ユーザー** ] ボックスでユーザーを選択する必要があります。 1 つまたは複数のレコードの種類を選択できます。

   - 単一のレコードの種類を選択した場合は、[ **アクティビティ** ] フィールドが動的に表示されます。 ドロップダウン リストを使用して、選択したレコードの種類からポリシーを適用するアクティビティを選択できます。 特定のアクティビティを選択しない場合は、選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。

   - 複数のレコードの種類を選択した場合、アクティビティを選択することはできません。 選択したレコードの種類のすべてのアクティビティにポリシーが適用されます。

   5. **期間:** ポリシーの条件を満たす監査ログの保持期間です。

   6. **ポリシー:** この値は、組織内の監査ログの保持ポリシーが処理される順序を決定します。 値が高いほど、高い優先度を示します。 たとえば、優先度の値が **5** のポリシーは、優先度の値が **0** のポリシーよりも優先されます。 前述のとおり、カスタム監査ログの保持ポリシーは、組織の既定ポリシーよりも優先されます。

4. [ **保存** ] をクリックして新しい監査ログの保持ポリシーを作成します。

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>PowerShell で監査ログの保持ポリシーを作成する

セキュリティ/コンプライアンス センターの PowerShell を使用して監査ログの保持ポリシーを作成することもできます。

1. [セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. 次のコマンドを実行して監査ログの保持ポリーを作成します。

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TenYears -Priority 100
   ```

    この例では、次の設定を使用して「Microsoft Teams 監査ポリシー」という名前の監査ログの保持ポリシーを作成します。

   - ポリシーの説明。

   - Microsoft Teams のすべてのアクティビティ ( *RecordType* パラメーターで定義) を保持します。

   - Microsoft Teams 監査ログを 10 年間保持します。

   - 優先度が 100 の場合。

監査ログの保持ポリシーを作成するもう 1 つの例を示します。 このポリシーには、ユーザー「admin@contoso.onmicrosoft.com」の 6 か月間の「ユーザー ログイン」アクティビティの監査ログが保持されます。

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

詳細については、「[New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy)」を参照してください。

## <a name="view-audit-log-retention-policies"></a>監査ログの保持ポリシーを表示する

現時点では、カスタム監査ログの保持ポリシーを表示する唯一の方法は、セキュリティ センターとコンプライアンス センターの PowerShell で **Get-UnifiedAuditRetentionPolicy** コマンドレットを使用することです。 組織の監査ログの保持ポリシーの設定 (前の手順で構成済み) を表示するサンプル コマンドを示します。 このコマンドを実行すると、ポリシーが優先度の高い順に並べ替えられます。

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> 現時点では、 **Get-UnifiedAuditLogRetentionPolicy** コマンドレットは、組織の既定の監査ログのポリシーを返しません。

詳細については、「[Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy)」を参照してください。

## <a name="some-audit-log-retention-policies-not-supported-in-the-ui"></a>UI でサポートされていない一部の監査ログの保持ポリシー

**New-UnifiedAuditLogRetentionPolicy** コマンドレットを使用すると、Microsoft 365 コンプライアンス センターの **[監査保持ポリシーの作成]** ツールでは使用できないレコードの種類またはアクティビティの監査ログ保持ポリシーを作成できます。 この場合、コンプライアンス センターの **[監査保持ポリシー]** タブからポリシーを編集 (保持期間の変更やアクティビティの追加と削除など) することはできません。 コンプライアンス センターでは、ポリシーを表示したり、削除したりすることはできません。 ポリシーを編集するには、セキュリティ/コンプライアンス センターの PowerShell で **Set-UnifiedAuditLogRetentionPolicy** コマンドレットを使用します。

## <a name="more-information"></a>詳細情報

- セキュリティ センターとコンプライアンス センターの PowerShell で **Set-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、既存の監査ログの保持ポリシーを変更します。 詳細については、「[Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy)」を参照してください。

- セキュリティ センターとコンプライアンス センターの PowerShell で **Remove-UnifiedAuditLogRetentionPolicy** コマンドレットを使用して、監査ログの保持ポリシーを削除します。 ポリシーが削除されるまで、最大 30 分かかる場合があります。 詳細については、「[Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy)」を参照してください。

- 前に説明したように、Azure Active Directory、Exchange、および SharePoint の運用に関する監査レコードは 1 年間保持されます。 次の表に、既定の監査ログの保持ポリシーに含まれるすべてのレコードの種類 (これらのサービスごと) を示します。 つまり、特定のレコードの種類、動作、またはユーザーに対してカスタム監査ログの保持ポリシーが優先されない限り、このレコードの種類の動作の監査ログは 1 年間保持されます。 各レコードの種類の Enum 値 (監査レコード内の RecordType プロパティの値として表示される) はかっこ内に表示されます。

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
   |AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
   |AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
   |AzureActiveDirectoryStsLogon (15)|Campaign (62)|Project (35)|
   ||ComplianceDLPExchange (13)|SharePoint (4)|
   ||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
   ||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
   ||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
   ||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
   ||ExchangeItemGroup (3)|SharePointListOperation (36)|
   ||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
   ||||
