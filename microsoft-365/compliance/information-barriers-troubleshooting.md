---
title: 情報バリアのトラブルシューティング
description: この記事は、情報バリアのトラブルシューティングのガイドとして使用します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191390"
---
# <a name="troubleshooting-information-barriers"></a>情報バリアのトラブルシューティング

[情報バリア](information-barriers.md) は、組織が法的要件や業界規制に準拠し続けるのに役立ちます。 たとえば、情報バリアを使用すると、特定のユーザー グループ間の通信を制限して、競合やその他の問題を回避できます。 (情報バリアを設定する方法の詳細については、「情報バリア [のポリシーを定義する](information-barriers-policies.md)」を参照してください)。

情報バリアが発生した後に予期しない問題が発生した場合は、それらの問題を解決するためにいくつかの手順を実行できます。 この記事をガイドとして使用してください。

> [!IMPORTANT]
> この記事で説明するタスクを実行するには、次のいずれかの適切なロールを割り当てる必要があります。<br/>- Microsoft 365 Enterprise グローバル管理者<br/>- グローバル管理者<br/>- コンプライアンス管理者<br/>- IB コンプライアンス管理 (これは新しいロールです!<p>情報バリアの前提条件の詳細については、「 [前提条件 (情報バリア ポリシーの場合)」](information-barriers-policies.md#prerequisites)を参照してください。<p>[セキュリティ & コンプライアンス センター PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)してください。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題: ユーザーが予期せず他のユーザーとの通信をブロックMicrosoft Teams 

この場合、ユーザーはMicrosoft Teamsで他のユーザーと通信する予期しない問題を報告しています。 次に例を示します。

- ユーザーは、Microsoft Teams内の別のユーザーを検索しますが、見つけることができません。
- ユーザーは、Microsoft Teams内の別のユーザーを検索できますが、選択することはできません。
- ユーザーは別のユーザーを表示できますが、Microsoft Teams内の他のユーザーにメッセージを送信することはできません。

### <a name="what-to-do"></a>操作

ユーザーが情報バリア ポリシーの影響を受けるかどうかを確認します。 ポリシーの構成方法によっては、情報バリアが期待どおりに機能している可能性があります。 または、組織のポリシーを絞り込む必要がある場合もあります。

1. Identity パラメーターで **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 名前、エイリアス、識別名 (DN)、標準 DN、電子メール アドレス、GUID など、各受信者を一意に識別する任意の ID 値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> この例では、Identity パラメーターにエイリアス (*meganb*) を使用しています。 このコマンドレットは、ユーザーが情報バリア ポリシーの影響を受けるかどうかを示す情報を返します。 (*ExoPolicyId: \<GUID>.) を探します。 |

    **ユーザーが情報バリア ポリシーに含まれていない場合は、サポートにお問い合わせください**。 それ以外の場合は、次の手順に進んでください。

2. 情報バリア ポリシーに含まれるセグメントを確認します。 これを行うには、Identity パラメーターと共に `Get-InformationBarrierPolicy` コマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 前の手順で受け取ったポリシー GUID (ExoPolicyId) などの詳細を ID 値として使用します。 | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* を持つ情報バリア ポリシーに関する詳細情報を取得しています。 |

    コマンドレットを実行した後、結果で **AssignedSegment**、 **SegmentsAllowed**、および **SegmentsBlocked** の値を探します。

    たとえば、コマンドレットを実行した `Get-InformationBarrierPolicy` 後、結果の一覧に次の情報が表示されます。

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    この場合、情報バリア ポリシーが Sales and Research セグメントのユーザーに影響を与えることがわかります。 この場合、Sales のユーザーは Research のユーザーと通信できなくなります。

    これが正しいと思われる場合は、情報バリアが期待どおりに機能します。 そうでない場合は、次の手順に進みます。

3. セグメントが正しく定義されていることを確認します。 これを行うには、コマンドレットを `Get-OrganizationSegment` 使用し、結果の一覧を確認します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> このコマンドレットは、Identity パラメーターと共に使用します。 | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* を持つセグメントに関する情報を取得しています。 |

    セグメントの詳細を確認します。 必要に応じて、 [セグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment)し、コマンドレットを `Start-InformationBarrierPoliciesApplication` 再利用します。

    **情報バリア ポリシーに問題がある場合は、サポートにお問い合わせください**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: Microsoft Teamsでブロックする必要があるユーザー間の通信が許可される

この場合、情報バリアは定義され、アクティブであり、適用されますが、相互に通信できないようにする必要があるユーザーは、何らかの形でMicrosoft Teamsでチャットや通話を行うことができます。

### <a name="what-to-do"></a>操作

問題のユーザーが情報バリア ポリシーに含まれていることを確認します。 

1. Id パラメーターで **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。

    |**Syntax** _|_ *Example**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、Office 365の 2 つのユーザー アカウント (*meganb* for *Megan* と *alexw*) を参照します。 |

    > [!TIP]
    > このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 結果を確認します。 **Get-InformationBarrierRecipientStatus** コマンドレットは、属性値や適用されるすべての情報バリア ポリシーなど、ユーザーに関する情報を返します。

    次の表に示すように、結果を確認し、次の手順を実行します。

    |**結果**|**次に実行する操作**|
    |:----------|:------------------|
    | 選択したユーザーのセグメントが一覧表示されない | 次のいずれかの操作を行います。<br/>- Azure Active Directoryでユーザー プロファイルを編集して、既存のセグメントにユーザーを割り当てます。 ([powerShell を使用したユーザー アカウントのプロパティの構成Office 365](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)参照してください)。<br/>- [情報バリアでサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義します。 次に、 [新しいポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies) するか [、既存のポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy) してそのセグメントを含めます。 |
    | セグメントは一覧表示されますが、情報バリア ポリシーはそれらのセグメントに割り当てされません | 次のいずれかの操作を行います。<br/>- 問題の各セグメント[に対して新しい情報バリア ポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies)する <br/>- [既存の情報バリア ポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy) して、適切なセグメントに割り当てる |
    | セグメントが一覧表示され、それぞれが情報バリア ポリシーに含まれています | - コマンドレットを `Get-InformationBarrierPolicy` 実行して、情報バリア ポリシーがアクティブであることを確認します<br/>- コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行してポリシーが適用されていることを確認する<br/>- コマンドレットを `Start-InformationBarrierPoliciesApplication` 実行して、すべてのアクティブな情報バリア ポリシーを適用する |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題: 情報バリア ポリシーから 1 人のユーザーを削除する必要がある

この場合、情報バリア ポリシーが有効になり、1 人以上のユーザーが予期せずMicrosoft Teamsで他のユーザーとの通信をブロックされます。 情報バリア ポリシーを完全に削除するのではなく、情報バリア ポリシーから 1 人以上の個々のユーザーを削除できます。

### <a name="what-to-do"></a>操作

情報バリア ポリシーは、ユーザーのセグメントに割り当てられます。 セグメントは、 [ユーザー アカウント プロファイルで特定の属性を](information-barriers-attributes.md)使用して定義されます。 1 人のユーザーからポリシーを削除する必要がある場合は、情報バリアの影響を受けるセグメントにユーザーが含まれなくなっているよう、Azure Active Directoryでそのユーザーのプロファイルを編集することを検討してください。

1. Id パラメーターで **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 このコマンドレットは、属性値や適用される情報バリア ポリシーなど、ユーザーに関する情報を返します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、Office 365の 2 つのユーザー アカウント (*meganb* for *Megan* と *alexw*) を参照します。          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、ユーザーを一意に識別する任意の値を使用できます。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> この例では、Office 365の 1 つのアカウントを参照しています。*ジャンプ*。 |

2. 結果を確認して、情報バリア ポリシーが割り当てられているかどうか、およびユーザーがどのセグメントに属しているか確認します。

3. 情報バリアの影響を受けるセグメントからユーザーを削除するには、[Azure Active Directoryでユーザーのプロファイル情報を更新](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)します。

4. FwdSync が発生するまで約 30 分待ちます。 または、コマンドレットを `Start-InformationBarrierPoliciesApplication` 実行して、すべてのアクティブな情報バリア ポリシーを適用します。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 情報バリアのアプリケーション プロセスに時間がかかりすぎる

**Start-InformationBarrierPoliciesApplication** コマンドレットを実行した後、プロセスが完了するまでに非常に長い時間がかかります。

### <a name="what-to-do"></a>操作

ポリシー アプリケーション コマンドレットを実行すると、組織内のすべてのアカウントに対して、ユーザーごとの情報バリア ポリシーが適用 (または削除) されることに注意してください。 ユーザーが多い場合は、処理に時間がかかります。 (一般的なガイドラインとして、5,000 個のユーザー アカウントを処理するのに約 1 時間かかります)。

1. **Get-InformationBarrierPoliciesApplicationStatus** コマンドレットを使用して、最新のポリシー アプリケーションの状態を確認します。

    |**最新のポリシー アプリケーションを表示するには**|**すべてのポリシー アプリケーションの状態を表示するには**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    これにより、ポリシー アプリケーションが完了したか、失敗したか、進行中であるかに関する情報が表示されます。

2. 前の手順の結果に応じて、次のいずれかの手順を実行します。
  
    |**状態**|**次の手順**|
    |:---------|:------------|
    | **未開始** | **Start-InformationBarrierPoliciesApplication** コマンドレットが実行されてから 45 分を超えた場合は、監査ログを確認して、ポリシー定義にエラーがないか、またはアプリケーションが起動していないその他の理由があるかどうかを確認します。 |
    | **Failed** | アプリケーションが失敗した場合は、監査ログを確認します。 セグメントとポリシーも確認します。 複数のセグメントに割り当てられているユーザーはいますか? セグメントに複数のポリシーが割り当てられているか。 必要に応じて、 [セグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment) したり、 [ポリシーを編集](information-barriers-edit-segments-policies.md#edit-a-policy)したりしてから、 **Start-InformationBarrierPoliciesApplication** コマンドレットをもう一度実行します。 |
    | **処理中** | アプリケーションがまだ進行中の場合は、完了するまでの時間を増やします。 数日経過した場合は、監査ログを収集してから、サポートにお問い合わせください。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題: 情報バリア ポリシーがまったく適用されていない

この場合、セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーを適用しようとしました。 ただし、コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行すると、ポリシー アプリケーションが失敗したことを確認できます。

### <a name="what-to-do"></a>操作

組織に[Exchangeアドレス帳ポリシー](/exchange/address-books/address-book-policies/address-book-policies)が設定されていないことを確認します。 このようなポリシーにより、情報バリア ポリシーが適用されなくなります。

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する

2. [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) コマンドレットを実行し、結果を確認します。

    |**結果**|**次の手順**|
    |:----------|:------------|
    | Exchangeアドレス帳ポリシーが一覧表示されます | [アドレス帳ポリシーを削除する](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | アドレス帳ポリシーが存在しない |監査ログを確認して、ポリシー アプリケーションが失敗する理由を確認する |

3. [ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)します。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>問題: 指定されたすべてのユーザーに対して情報バリア ポリシーが適用されない

セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーを適用しようとすると、ポリシーが一部の受信者に適用されているが、他の受信者には適用されない場合があります。
コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行するときは、次のようなテキストを出力で検索します。

> Id： `<application guid>`
>
> 受信者の合計数: 81527
>
> 失敗した受信者: 2
>
> エラー カテゴリ: なし
>
> 状態: 完了

### <a name="what-to-do"></a>操作

1. 監査ログ `<application guid>`で検索します。 この PowerShell コードをコピーし、変数の変更を行うことができます。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 監査ログからの詳細な出力で、フィールドの `"UserId"` 値を `"ErrorDetails"` 確認します。 これにより、エラーの理由が表示されます。 この PowerShell コードをコピーし、変数の変更を行うことができます。

```powershell
   $DetailedLogs[1] |fl
```

例:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. エラー: IB セグメント "セグメント ID1" と IB セグメント "セグメント ID2" に競合があり、受信者に割り当てることができません。

3. 通常、ユーザーが複数のセグメントに含まれていることがわかります。 この問題を解決するには、次の値`OrganizationSegments`を`-UserGroupFilter`更新します。

4. 情報バリア ポリシーの手順を使用して [、情報バリア ポリシー](information-barriers-policies.md#part-3-apply-information-barrier-policies)を再適用します。

## <a name="resources"></a>リソース

- [Microsoft Teamsで情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報障壁](information-barriers.md)