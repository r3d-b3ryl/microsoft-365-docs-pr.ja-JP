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

[情報の障壁は](information-barriers.md) 、組織が法的要件と業界規制に準拠し続けるのに役立ちます。 たとえば、情報バリアを使用すると、特定のユーザー グループ間の通信を制限して、利益相反や他の問題を回避できます。 (情報バリアを設定する方法の詳細については、「情報バリアのポリシーを定義する」 [を参照](information-barriers-policies.md)してください。

情報バリアが発生した後に予期しない問題が発生した場合は、それらの問題を解決するためのいくつかの手順を実行できます。 この記事をガイドとして使用します。

> [!IMPORTANT]
> この記事で説明するタスクを実行するには、次のいずれかの適切な役割を割り当てる必要があります。<br/>- Microsoft 365 Enterpriseグローバル管理者<br/>- グローバル管理者<br/>- コンプライアンス管理者<br/>- IB コンプライアンス管理 (これは新しい役割です!<p>情報バリアの前提条件の詳細については、「前提条件 (情報バリア ポリシーの場合 [)」を参照してください](information-barriers-policies.md#prerequisites)。<p>コンプライアンス センター [PowerShell のセキュリティ &接続してください](/powershell/exchange/connect-to-scc-powershell)。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>問題: ユーザーが予期せず、他のユーザーとの通信をブロックMicrosoft Teams 

この場合、ユーザーは他のユーザーと通信する予期しない問題を報告Microsoft Teams。 次に例を示します。

- ユーザーは、ユーザー内の別のユーザーを検索しますが、見Microsoft Teams。
- ユーザーは、他のユーザーを検索できますが、選択Microsoft Teams。
- ユーザーは別のユーザーを表示できますが、他のユーザーにメッセージを送信Microsoft Teams。

### <a name="what-to-do"></a>操作

ユーザーが情報バリア ポリシーの影響を受けるかどうかを判断します。 ポリシーの構成方法によっては、予想通り情報バリアが機能している可能性があります。 または、組織のポリシーを絞り込む必要がある場合があります。

1. Identity パラメーター **と一緒に Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> 名前、エイリアス、識別名 (DN)、標準 DN、電子メール アドレス、GUID など、各受信者を一意に識別する任意の ID 値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> この例では、Identity パラメーターにエイリアス (*meganb*) を使用しています。 このコマンドレットは、ユーザーが情報バリア ポリシーの影響を受けるかどうかを示す情報を返します。 (*ExoPolicyId: \<GUID> .) を探します。 |

    **ユーザーが情報バリア ポリシーに含まれていない場合は、サポートにお問い合わせください**。 それ以外の場合は、次の手順に進んでください。

2. 情報バリア ポリシーに含まれるセグメントを確認します。 これを行うには、Identity パラメーター `Get-InformationBarrierPolicy` と一緒にコマンドレットを使用します。 

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> 前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を ID 値として使用します。 | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f* を持つ情報バリア ポリシーに関する詳細情報を取得しています。 |

    コマンドレットを実行した後、結果で **AssignedSegment、SegmentsAllowed、****および SegmentsBlocked** の値を探します。 

    たとえば、コマンドレットを実行した `Get-InformationBarrierPolicy` 後、結果の一覧で次の結果を確認しました。

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    この場合、情報バリア ポリシーが Sales および Research セグメントに含まれるユーザーに影響を与えるのが分かっています。 この場合、Sales のユーザーは Research のユーザーとの通信を妨げされます。

    これが正しいと思われる場合は、情報バリアが期待通り機能しています。 そうでない場合は、次の手順に進みます。

3. セグメントが正しく定義されていることを確認します。 これを行うには、コマンドレットを `Get-OrganizationSegment` 使用して、結果の一覧を確認します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Identity パラメーターと一緒にこのコマンドレットを使用します。 | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* を持つセグメントに関する情報を取得しています。 |

    セグメントの詳細を確認します。 必要に応 [じて、セグメントを編集](information-barriers-edit-segments-policies.md#edit-a-segment)し、コマンドレットを再使用 `Start-InformationBarrierPoliciesApplication` します。

    **まだ情報バリア ポリシーに問題がある場合は、サポートにお問い合わせください**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: ユーザー間でブロックする必要があるユーザー間の通信Microsoft Teams

この場合、情報バリアは定義され、アクティブにされ、適用されますが、通信を妨げる必要があるユーザーは、Microsoft Teams で何らかの形でお互いにチャットし、通話することができます。

### <a name="what-to-do"></a>操作

問題のユーザーが情報バリア ポリシーに含まれているか確認します。 

1. Identity パラメーター **を使用して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。

    |**構文** _|_ *例**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、次の 2 つのユーザー アカウントを参照Office 365 *meganb* for *Megan、Alex* の alexw *です。*  |

    > [!TIP]
    > 1 人のユーザーに対してこのコマンドレットを使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>`

2. 結果を確認します。 **Get-InformationBarrierRecipientStatus** コマンドレットは、属性値や適用される情報バリア ポリシーなど、ユーザーに関する情報を返します。

    次の表で説明するように、結果を確認し、次の手順を実行します。

    |**結果**|**次に実行する操作**|
    |:----------|:------------------|
    | 選択したユーザーに対してセグメントが一覧表示されません。 | 次のいずれかの操作を行います。<br/>- ユーザー プロファイルを編集して既存のセグメントにユーザーを割り当Azure Active Directory。 [(「PowerShell を使用してユーザー アカウントのプロパティOffice 365構成する」を参照](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)してください。<br/>- 情報バリアでサポートされている [属性を使用してセグメントを定義します](information-barriers-attributes.md)。 次に、新 [しいポリシーを定義するか、](information-barriers-policies.md#part-2-define-information-barrier-policies) 既存 [のポリシーを編集して](information-barriers-edit-segments-policies.md#edit-a-policy) そのセグメントを含めるかのどちらかです。 |
    | セグメントは一覧表示されますが、それらのセグメントに情報バリア ポリシーが割り当てられていない | 次のいずれかの操作を行います。<br/>- [問題のセグメントごとに新しい情報](information-barriers-policies.md#part-2-define-information-barrier-policies) バリア ポリシーを定義する <br/>- [既存の情報バリア ポリシーを編集して、](information-barriers-edit-segments-policies.md#edit-a-policy) 適切なセグメントに割り当てる |
    | セグメントが一覧表示され、それぞれが情報バリア ポリシーに含まれる | - コマンドレットを `Get-InformationBarrierPolicy` 実行して、情報バリア ポリシーがアクティブな状態を確認する<br/>- コマンドレットを `Get-InformationBarrierPoliciesApplicationStatus` 実行してポリシーが適用されるのを確認する<br/>- コマンドレットを `Start-InformationBarrierPoliciesApplication` 実行して、すべてのアクティブな情報バリア ポリシーを適用する |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>問題: 情報バリア ポリシーから 1 人のユーザーを削除する必要がある

この場合、情報バリア ポリシーが有効であり、1 人または複数のユーザーが予期せず他のユーザーとの通信をブロックMicrosoft Teams。 情報バリア ポリシーを完全に削除するのではなく、1 人または複数の個々のユーザーを情報バリア ポリシーから削除できます。

### <a name="what-to-do"></a>操作

情報バリア ポリシーは、ユーザーのセグメントに割り当てられます。 セグメントは、ユーザー アカウント プロファイルで特定 [の属性を使用して定義されます](information-barriers-attributes.md)。 1 人のユーザーからポリシーを削除する必要がある場合は、Azure Active Directory でユーザーのプロファイルを編集して、情報バリアの影響を受けるセグメントにユーザーが含まれていないか検討してください。

1. Identity パラメーター **を使用して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 このコマンドレットは、属性値や適用される情報バリア ポリシーなど、ユーザーに関する情報を返します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、次の 2 つのユーザー アカウントを参照Office 365 *meganb* for *Megan、Alex* の alexw *です。*           |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> 名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、ユーザーを一意に識別する任意の値を使用できます。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> この例では、jeanp の 1 つのアカウントOffice 365 *参照します*。 |

2. 結果を確認して、情報バリア ポリシーが割り当てられているか、ユーザーが属するセグメントを確認します。

3. 情報バリアの影響を受けるセグメントからユーザーを削除するには、ユーザーのプロファイル情報を更新[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. FwdSync が発生するまで約 30 分待ちます。 または、コマンドレットを実行 `Start-InformationBarrierPoliciesApplication` してすべてのアクティブな情報バリア ポリシーを適用します。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 情報バリア アプリケーション プロセスに時間がかかっている

**Start-InformationBarrierPoliciesApplication** コマンドレットを実行した後、プロセスが完了するには本当に長い時間が必要です。

### <a name="what-to-do"></a>操作

ポリシー アプリケーションコマンドレットを実行すると、組織内のすべてのアカウントに対して、ユーザー別に情報バリア ポリシーが適用 (または削除) されます。 ユーザーが多い場合は、処理に時間がかかる場合があります。 (一般的なガイドラインとして、5,000 のユーザー アカウントを処理するのに約 1 時間かかる)。

1. **Get-InformationBarrierPoliciesApplicationStatus** コマンドレットを使用して、最新のポリシー アプリケーションの状態を確認します。

    |**最新のポリシー アプリケーションを表示するには**|**すべてのポリシー アプリケーションの状態を表示するには**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    これにより、ポリシー アプリケーションが完了、失敗、または進行中かどうかに関する情報が表示されます。

2. 前の手順の結果に応じて、次のいずれかの手順を実行します。
  
    |**状態**|**次の手順**|
    |:---------|:------------|
    | **開始されていない** | **Start-InformationBarrierPoliciesApplication** コマンドレットの実行から 45 分を超える時間が経っている場合は、監査ログを確認して、ポリシー定義にエラーが発生したのか、またはアプリケーションが起動していないその他の理由を確認してください。 |
    | **Failed** | アプリケーションが失敗した場合は、監査ログを確認します。 また、セグメントとポリシーも確認します。 複数のセグメントに割り当てられているユーザーはいますか? 複数の poliicy が割り当てられているセグメントはありますか? 必要に応 [じて、セグメントの編集](information-barriers-edit-segments-policies.md#edit-a-segment)や [](information-barriers-edit-segments-policies.md#edit-a-policy)ポリシーの編集を行い **、Start-InformationBarrierPoliciesApplication** コマンドレットを再度実行します。 |
    | **処理中** | アプリケーションがまだ進行中の場合は、完了する時間を多くします。 数日が過ごした場合は、監査ログを収集し、サポートにお問い合わせください。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>問題: 情報バリア ポリシーが適用されていない

この場合、セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーの適用を試みた。 ただし、コマンドレットを実行すると `Get-InformationBarrierPoliciesApplicationStatus` 、ポリシー アプリケーションが失敗しているのが確認できます。

### <a name="what-to-do"></a>操作

組織にアドレス帳ポリシーがExchange[されていないことを](/exchange/address-books/address-book-policies/address-book-policies)確認します。 このようなポリシーは、情報バリア ポリシーが適用されるのを防ぐ。

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) に接続する

2. [Get-AddressBookPolicy コマンドレットを実行](/powershell/module/exchange/get-addressbookpolicy)し、結果を確認します。

    |**結果**|**次の手順**|
    |:----------|:------------|
    | Exchangeアドレス帳ポリシーが一覧表示される | [アドレス帳ポリシーを削除する](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | アドレス帳ポリシーが存在しない |監査ログを確認して、ポリシー アプリケーションが失敗する理由を確認する |

3. [ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示します](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>問題: すべての指定ユーザーに適用されない情報バリア ポリシー

セグメントを定義し、情報バリア ポリシーを定義し、それらのポリシーを適用しようとすると、ポリシーが一部の受信者に適用されますが、他の受信者には適用されない場合があります。
コマンドレットを実行する `Get-InformationBarrierPoliciesApplicationStatus` 場合は、出力で次のようなテキストを検索します。

> ID: `<application guid>`
>
> 受信者の総数: 81527
>
> 失敗した受信者: 2
>
> エラー カテゴリ: なし
>
> 状態: 完了

### <a name="what-to-do"></a>操作

1. 監査ログで検索します `<application guid>` 。 この PowerShell コードをコピーして、変数を変更できます。

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. 監査ログからの詳細な出力で、フィールドの値を `"UserId"` 確認 `"ErrorDetails"` します。 これにより、エラーの理由が示されます。 この PowerShell コードをコピーして、変数を変更できます。

```powershell
   $DetailedLogs[1] |fl
```

例:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict。 エラー: IB セグメント "セグメント id1" と IB セグメント "セグメント id2" が競合し、受信者に割り当てできません。

3. 通常、ユーザーが複数のセグメントに含まれている場合があります。 この問題は、 で値を更新 `-UserGroupFilter` することで修正できます `OrganizationSegments` 。

4. これらの手順を使用して情報バリア ポリシーを再適用 [する 情報バリア ポリシー](information-barriers-policies.md#part-3-apply-information-barrier-policies)。

## <a name="resources"></a>リソース

- [情報バリアのポリシーを定義Microsoft Teams](information-barriers-policies.md)
- [情報障壁](information-barriers.md)