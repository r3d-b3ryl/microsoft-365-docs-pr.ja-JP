---
title: 情報バリアのトラブルシューティング
description: この記事は、情報障壁のトラブルシューティングのガイドとして使用します。
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
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126564"
---
# <a name="troubleshooting-information-barriers"></a>情報バリアのトラブルシューティング

[情報障壁は、](information-barriers.md) 組織が法的要件や業界の規制に準拠し続けるのに役立ちます。 たとえば、情報バリアを使用すると、特定のユーザー グループ間の通信を制限して、利益の競合や他の問題を回避できます。 (情報バリアを設定する方法の詳細については、「情報バリアのポリシーの定義」 [を参照してください](information-barriers-policies.md))。

情報バリアが設定された後に予期しない問題が発生した場合は、それらの問題を解決するためにいくつかの手順を実行できます。 この記事をガイドとして使用します。

> [!IMPORTANT]
> この記事で説明するタスクを実行するには、次のいずれかの適切な役割が割り当てられている必要があります。<br/>- Microsoft 365 Enterprise グローバル管理者<br/>- グローバル管理者<br/>- コンプライアンス管理者<br/>-IB コンプライアンス管理 (これは新しい役割です)<p>情報バリアの前提条件の詳細については、「前提条件 (情報バリア ポリシーの [場合)」](information-barriers-policies.md#prerequisites)を参照してください。<p>セキュリティ センター [コンプライアンス センターの PowerShell &接続してください](/powershell/exchange/connect-to-scc-powershell)。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題: Microsoft Teams の他のユーザーとの通信が予期せずブロックされる 

この場合、Microsoft Teams で他のユーザーと通信する際に予期しない問題が報告されています。 次に例を示します。

- ユーザーが Microsoft Teams で別のユーザーを検索しますが、見つからない場合。
- ユーザーは Microsoft Teams で別のユーザーを検索できますが、選択することはできません。
- ユーザーは別のユーザーを表示できますが、Microsoft Teams で他のユーザーにメッセージを送信することはできません。

### <a name="what-to-do"></a>操作

ユーザーが情報バリア ポリシーの影響を受けるかどうかを判断します。 ポリシーの構成方法によっては、情報バリアが期待通り動作している可能性があります。 または、組織のポリシーを調整する必要がある場合があります。

1. Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 名前、エイリアス、識別名 (DN)、正規 DN、電子メール アドレス、GUID など、各受信者を一意に識別する任意の ID 値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> この例では、Identity パラメーターにエイリアス (*meganb)* を使用しています。 このコマンドレットは、ユーザーが情報バリア ポリシーの影響を受けるかどうかを示す情報を返します。 (*ExoPolicyId: を探します \<GUID> 。 |

    **ユーザーが情報バリア ポリシーに含まれていない場合は、サポートにお問い合わせください**。 それ以外の場合は、次の手順に進んでください。

2. 情報バリア ポリシーに含まれるセグメントを確認します。 これを行うには `Get-InformationBarrierPolicy` 、Identity パラメーターを指定してコマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を ID 値として使用します。 | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* を持つ情報バリア ポリシーに関する詳細情報を取得しています。 |

    コマンドレットを実行した後、結果で **AssignedSegment、SegmentsAllowed、****および SegmentsBlocked** の値を探します。 

    たとえば、コマンドレットの実行後 `Get-InformationBarrierPolicy` 、結果の一覧に次の結果が表示されます。

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    この場合、情報バリア ポリシーが Sales および Research セグメントに含まれるユーザーに影響を与えるのを確認できます。 この場合、Sales のユーザーは Research のユーザーと通信できます。

    これが正しいと思われる場合、情報バリアは期待通り動作しています。 そうでない場合は、次の手順に進みます。

3. セグメントが正しく定義されていることを確認します。 これを行うには、コマンドレットを `Get-OrganizationSegment` 使用し、結果の一覧を確認します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> このコマンドレットは Identity パラメーターと一緒に使用します。 | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> この例では、GUID *が c96e0837-c232-4a8a-841e-ef45787d8fcd* であるセグメントに関する情報を取得しています。 |

    セグメントの詳細を確認します。 必要に応 [じてセグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment)し、コマンドレットを再使用 `Start-InformationBarrierPoliciesApplication` します。

    **If you are still having issues with your information barrier policy, contact support**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: Microsoft Teams でブロックする必要があるユーザー間の通信が許可されている

この場合、情報バリアが定義され、アクティブで、適用されている場合でも、互いに通信を妨げる必要があるユーザーは、Microsoft Teams でチャットし、互いに通話することができます。

### <a name="what-to-do"></a>操作

該当するユーザーが情報バリア ポリシーに含まれているか確認します。 

1. Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。

    |**構文** _|_ *の例**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、365 年 365 日に Office 2 つのユーザー アカウント *(megan* の場合は *meganb、Alex* の場合は *alexw)* を参照 *します*。 |

    > [!TIP]
    > このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 結果を確認します。 **Get-InformationBarrierRecipientStatus** コマンドレットは、属性値や適用されている情報バリア ポリシーなど、ユーザーに関する情報を返します。

    結果を確認し、次の表に示す手順を実行します。

    |**結果**|**次の操作**|
    |:----------|:------------------|
    | 選択したユーザーのセグメントが一覧表示されません。 | 次のいずれかの操作を行います。<br/>- Azure Active Directory でユーザー プロファイルを編集して、既存のセグメントにユーザーを割り当てる。 [(「365 PowerShell を使用してユーザー Officeを構成する」を参照](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)してください)。<br/>- 情報バリアでサポートされている [属性を使用してセグメントを定義します](information-barriers-attributes.md)。 次に、新[しいポリシーを定義するか](information-barriers-policies.md#part-2-define-information-barrier-policies)[、既存のポリシーを編集して](information-barriers-edit-segments-policies.md#edit-a-policy)そのセグメントを含めるかのどちらかです。 |
    | セグメントが一覧表示されますが、それらのセグメントに情報バリア ポリシーが割り当てられていない | 次のいずれかの操作を行います。<br/>- [問題のセグメントごとに新しい](information-barriers-policies.md#part-2-define-information-barrier-policies) 情報バリア ポリシーを定義する <br/>- [既存の情報バリア ポリシーを編集して適切](information-barriers-edit-segments-policies.md#edit-a-policy) なセグメントに割り当てる |
    | セグメントが一覧表示され、それぞれが情報バリア ポリシーに含まれる | - コマンドレットを `Get-InformationBarrierPolicy` 実行して情報バリア ポリシーがアクティブな状態を確認する<br/>- コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行してポリシーが適用されたのを確認する<br/>- コマンドレットを実行 `Start-InformationBarrierPoliciesApplication` してすべてのアクティブな情報バリア ポリシーを適用する |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題: 情報バリア ポリシーから 1 人のユーザーを削除する必要がある

この場合、情報バリア ポリシーが有効であり、1 人または複数のユーザーが Microsoft Teams の他のユーザーとの通信を予期せずブロックされます。 情報バリア ポリシーを完全に削除するのではなく、1 人または複数の個々のユーザーを情報バリア ポリシーから削除できます。

### <a name="what-to-do"></a>操作

情報バリア ポリシーは、ユーザーのセグメントに割り当てられます。 セグメントは、ユーザー アカウント プロファイルの特定 [の属性を使用して定義されます](information-barriers-attributes.md)。 1 人のユーザーからポリシーを削除する必要がある場合は、そのユーザーのプロファイルを Azure Active Directory で編集して、情報バリアの影響を受けるセグメントにユーザーが含めなくなるのを検討してください。

1. Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 このコマンドレットは、属性値や適用されている情報バリア ポリシーなど、ユーザーに関する情報を返します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、365 年 365 日に Office 2 つのユーザー アカウント *(megan* の場合は *meganb、Alex* の場合は *alexw)* を参照 *します*。          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、ユーザーを一意に識別する任意の値を使用できます。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> この例では、365 年 1 月 365 Officeアカウントを *参照します*。 |

2. 結果を確認して、情報バリア ポリシーが割り当てられているか、ユーザーが属するセグメントを確認します。

3. 情報バリアの影響を受けるセグメントからユーザーを削除するには、Azure Active Directory でユーザーのプロファイル [情報を更新します](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

4. FwdSync が発生するまで約 30 分待ちます。 または、コマンドレットを実行 `Start-InformationBarrierPoliciesApplication` してすべてのアクティブな情報バリア ポリシーを適用します。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 情報バリア アプリケーション プロセスに時間がかかっている

**Start-InformationBarrierPoliciesApplication** コマンドレットを実行した後、プロセスが完了するには非常に長い時間が必要です。

### <a name="what-to-do"></a>操作

ポリシー アプリケーションコマンドレットを実行すると、組織内のすべてのアカウントに対して、ユーザー別に情報バリア ポリシーが適用 (または削除) されます。 ユーザーが多い場合は、処理に時間がかかる場合があります。 (一般的なガイドラインとして、5,000 のユーザー アカウントの処理には約 1 時間かかる)。

1. **Get-InformationBarrierPoliciesApplicationStatus** コマンドレットを使用して、最新のポリシー アプリケーションの状態を確認します。

    |**最新のポリシー アプリケーションを表示するには**|**すべてのポリシー アプリケーションの状態を表示するには**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    これにより、ポリシー アプリケーションが完了した、失敗した、または進行中かどうかに関する情報が表示されます。

2. 前の手順の結果に応じて、次のいずれかの手順を実行します。
  
    |**状態**|**次の手順**|
    |:---------|:------------|
    | **開始されていない** | **Start-InformationBarrierPoliciesApplication** コマンドレットの実行から 45 分以上経っている場合は、監査ログを確認して、ポリシー定義にエラーが発生していないか、またはアプリケーションが起動していない理由を確認します。 |
    | **Failed** | アプリケーションが失敗した場合は、監査ログを確認します。 また、セグメントとポリシーも確認します。 複数のセグメントに割り当てられているユーザーはいますか? 複数のポリシーが割り当てられているセグメントはありますか? 必要に応 [じて、セグメント](information-barriers-edit-segments-policies.md#edit-a-segment)の編集や [](information-barriers-edit-segments-policies.md#edit-a-policy)ポリシーの編集を行い **、Start-InformationBarrierPoliciesApplication** コマンドレットを再度実行します。 |
    | **処理中** | アプリケーションがまだ進行中の場合は、完了までさらに時間を取る必要があります。 数日が過ごした場合は、監査ログを収集し、サポートにお問い合わせください。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題: 情報バリア ポリシーが適用されていない

この場合、セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーの適用を試みたとします。 ただし、コマンドレットを実行すると `Get-InformationBarrierPoliciesApplicationStatus` 、ポリシー アプリケーションが失敗しているのを確認できます。

### <a name="what-to-do"></a>操作

組織に Exchange アドレス帳ポリシー [が設定されていないことを](/exchange/address-books/address-book-policies/address-book-policies) 確認します。 このようなポリシーは、情報バリア ポリシーの適用を防止します。

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する

2. [Get-AddressBookPolicy コマンドレットを実行](/powershell/module/exchange/get-addressbookpolicy)し、結果を確認します。

    |**結果**|**次の手順**|
    |:----------|:------------|
    | Exchange アドレス帳ポリシーが一覧表示される | [アドレス帳ポリシーを削除する](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | アドレス帳ポリシーが存在しない |監査ログを確認して、ポリシー アプリケーションが失敗する理由を確認する |

3. [ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示します](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>問題: 指定されたユーザーに適用されない情報バリア ポリシー

セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーを適用しようとすると、ポリシーが一部の受信者に適用されますが、他の受信者には適用されない場合があります。
コマンドレットを実行すると `Get-InformationBarrierPoliciesApplicationStatus` 、出力で次のようなテキストが検索されます。

> ID: `<application guid>`
>
> Total Recipients: 81527
>
> 失敗した受信者: 2
>
> エラー カテゴリ: なし
>
> 状態: 完了

### <a name="what-to-do"></a>操作

1. 監査ログで検索します `<application guid>` 。 この PowerShell コードをコピーし、変数を変更できます。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 監査ログからの詳細な出力で、フィールドの値を `"UserId"` 確認 `"ErrorDetails"` します。 これにより、エラーの理由が示されます。 この PowerShell コードをコピーし、変数を変更できます。

```powershell
   $DetailedLogs[1] |fl
```

例:

> "UserId": User1
>
>"ErrorDetails":"Status:IBPolicyConflict. エラー: "segment id1" と"segment id2" の間に競合が発生し、受信者に割り当てできません。

3. 通常、ユーザーが複数のセグメントに含まれている場合があります。 You can fix this by updating the `-UserGroupFilter` value in `OrganizationSegments` .

4. これらの手順を使用して、情報バリア ポリシーを再 [適用します](information-barriers-policies.md#part-3-apply-information-barrier-policies)。

## <a name="resources"></a>リソース

- [Microsoft Teams での情報障壁のポリシーの定義](information-barriers-policies.md)
- [情報障壁](information-barriers.md)
