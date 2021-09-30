---
title: 情報バリア ポリシーの管理
description: 情報バリアのポリシーを編集または削除する方法について説明します。
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
ms.openlocfilehash: 79f82ba1133af3c3cfe1d8c7b05b481528bcb003
ms.sourcegitcommit: 4ea16de333421e24b15dd1f164963bc9678653fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2021
ms.locfileid: "60010107"
---
# <a name="manage-information-barrier-policies"></a>情報バリア ポリシーの管理

情報バリア[ポリシーを定義](information-barriers-policies.md)した後、トラブルシューティングの一環として、または定期的なメンテナンスとして、それらのポリシーまたはユーザー セグメントに変更[](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)を加える必要がある場合があります。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

|**操作**|**説明**|
|:---------|:--------------|
| [ユーザー アカウントの属性を編集する](#edit-user-account-attributes) | セグメントの定義にAzure Active Directory属性を入力します。<br/>ユーザーアカウントの属性を編集して、ユーザーがセグメントに含まれていない場合、ユーザーが所属するセグメントを変更したり、異なる属性を使用してセグメントを定義したりする場合。 |
| [セグメントを編集する](#edit-a-segment) | セグメントの定義方法を変更する場合は、セグメントを編集します。 <br/>たとえば、Department を使用して最初にセグメントを定義し *、MemberOf* などの別の属性を使用 *する場合があります*。 |
| [ポリシーを編集する](#edit-a-policy) | ポリシーの動作方法を変更する場合は、情報バリア ポリシーを編集します。<br/>たとえば、2 つのセグメント間の通信をブロックする代わりに、特定のセグメント間でのみ通信を行う必要がある場合があります。 |
| [ポリシーを非アクティブな状態に設定する](#set-a-policy-to-inactive-status) |ポリシーを変更する場合、またはポリシーを有効にしない場合は、ポリシーを非アクティブ状態に設定します。 |
| [ポリシーを削除する](#remove-a-policy) | 特定のポリシーが不要になった場合は、情報バリア ポリシーを削除します。 |
| [ポリシー アプリケーションを停止する](#stop-a-policy-application) | 情報バリア ポリシーの適用プロセスを停止する場合は、このアクションを実行します。<br/> ポリシー アプリケーションを停止しても、ユーザーに既に適用されているポリシーは元に戻されません。 |
| [情報バリアに対するポリシーを定義する](information-barriers-policies.md) | このようなポリシーが設定されていない場合に情報バリア ポリシーを定義し、特定のユーザー グループ間の通信を制限または制限する必要があります。 |
| [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) | 情報バリアで予期しない問題が発生した場合は、この記事を参照してください。 |

> [!IMPORTANT]
> この記事で説明するタスクを実行するには、次のいずれかの適切な役割を割り当てる必要があります。<br/>- Microsoft 365 Enterpriseグローバル管理者<br/>- グローバル管理者<br/>- コンプライアンス管理者<br/>- IB コンプライアンス管理 (これは新しい役割です!<br><br>情報バリアの前提条件の詳細については、「前提条件 (情報バリア ポリシーの場合 [)」を参照してください](information-barriers-policies.md#step-1-make-sure-prerequisites-are-met)。<br><br> コンプライアンス センター [PowerShell のセキュリティ &接続してください](/powershell/exchange/connect-to-scc-powershell)。

## <a name="edit-user-account-attributes"></a>ユーザー アカウントの属性を編集する

セグメント化ユーザーに使用する属性を編集するには、次の手順を実行します。 たとえば、Department 属性を使用している場合に、1 つ以上のユーザー アカウントに現在 Department の値が表示されていない場合は、それらのユーザー アカウントを編集して部署情報を含める必要があります。 ユーザー アカウントの属性は、情報バリア ポリシーを割り当て可能なセグメントを定義するために使用されます。

1. 属性値や割り当てられたセグメントなど、特定のユーザー アカウントの詳細を表示するには、Identity パラメーターを使用して **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p> (このコマンドレットは、1 人のユーザーにも使用できます `Get-InformationBarrierRecipientStatus -Identity <value>` 。 |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、次の 2 つのユーザー アカウントを参照Office 365 *meganb* for *Megan、Alex* の alexw *です。*  |

2. ユーザー アカウント プロファイルに対して編集する属性を決定します。 詳細については、「情報バリア ポリシー [の属性」を参照してください](information-barriers-attributes.md)。 

3. 1 つ以上のユーザー アカウントを編集して、前の手順で選択した属性の値を含める。 このアクションを実行するには、次のいずれかの手順を使用します。

    - 1 つのアカウントを編集するには、「ユーザープロファイルを使用してユーザーのプロファイル情報を追加または更新する」[を参照](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)Azure Active Directory。

    - 複数のアカウントを編集する (または PowerShell を使用して 1 つのアカウントを編集する) には、「PowerShell を使用してユーザー アカウントのプロパティを構成する[Office 365参照してください](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)。

## <a name="edit-a-segment"></a>セグメントを編集する

ユーザー セグメントの定義を編集するには、次の手順を実行します。 たとえば、セグメントの名前や、セグメントに含まれるユーザーを特定するために使用されるフィルターを変更できます。

1. 既存のすべてのセグメントを表示するには **、Get-OrganizationSegment コマンドレットを使用** します。

    構文: `Get-OrganizationSegment`

    セグメントの種類、UserGroupFilter の値、作成または最後に変更したユーザー、GUID など、各セグメントと詳細の一覧が表示されます。

    > [!TIP]
    > 後で参照するために、セグメントのリストを印刷または保存します。 たとえば、セグメントを編集する場合は、その名前を知る必要があります。または値を識別する必要があります (これは Identity パラメーターと一緒に使用されます)。

2. セグメントを編集するには、Identity パラメーターと関連する詳細を指定して **Set-OrganizationSegment** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* を持つセグメントについて、部門名を "HRDept" に更新しました。 |

組織のセグメントの編集が完了したら、情報バリア ポリシーを[定義](#edit-a-policy)または編集できます。 [](information-barriers-policies.md#step-3-define-information-barrier-policies)

## <a name="edit-a-policy"></a>ポリシーを編集する

1. 現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。

    構文: `Get-InformationBarrierPolicy`

    結果の一覧で、変更するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. Identity パラメーター **と一緒に Set-InformationBarrierPolicy** コマンドレットを使用し、行う変更を指定します。 

    例: Research セグメントが Sales セグメントおよび *Marketing* セグメントとの通信をブロックするポリシー *を定義した**と* します。 ポリシーは、次のコマンドレットを使用して定義されています。 `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    リサーチ セグメントのユーザーが人事セグメントのユーザーとのみ通信できるよう *変更するとします*。 この変更を行う場合は、次のコマンドレットを使用します。 `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し *、HR* セグメントを指定しました。

3. ポリシーの編集が完了したら、必ず変更を適用してください。 (「 [情報バリア ポリシーの適用」を参照](information-barriers-policies.md#step-4-apply-information-barrier-policies)してください。

## <a name="set-a-policy-to-inactive-status"></a>ポリシーを非アクティブな状態に設定する

1. 現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。

    構文: `Get-InformationBarrierPolicy`

    結果の一覧で、変更 (または削除) するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. ポリシーの状態を非アクティブに設定するには、Identity パラメーターと State パラメーターを非アクティブに設定した **Set-InformationBarrierPolicy** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247* を非アクティブな状態に設定します。 |

3. 変更を適用するには **、Start-InformationBarrierPoliciesApplication コマンドレットを使用** します。

    構文: `Start-InformationBarrierPoliciesApplication`

    変更は、組織に対してユーザー別に適用されます。 組織が大規模な場合、このプロセスが完了するには 24 時間以上かかる場合があります。 (一般的なガイドラインとして、5,000 のユーザー アカウントを処理するのに約 1 時間かかる)。

この時点で、1 つ以上の情報バリア ポリシーが非アクティブ状態に設定されます。 ここから、次の操作を実行できます。

- この状態を維持します (ポリシー セットを非アクティブな状態に設定すると、ユーザーには影響しません)
- [ポリシーの編集](#edit-a-policy) 
- [ポリシーを削除する](#remove-a-policy)

## <a name="remove-a-policy"></a>ポリシーを削除する

1. 現在の情報バリア ポリシーの一覧を表示するには **、Get-InformationBarrierPolicy コマンドレットを使用** します。

    構文: `Get-InformationBarrierPolicy`

    結果の一覧で、削除するポリシーを特定します。 ポリシーの GUID と名前をメモします。 ポリシーが非アクティブ状態に設定されている必要があります。

2. Identity パラメーター **と一緒に Remove-InformationBarrierPolicy** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* を持つポリシーを削除しています。 |

    メッセージが表示されたら、変更を確認します。

3. 削除するポリシーごとに手順 1 ~ 2 を繰り返します。

4. ポリシーの削除が完了したら、変更を適用します。 このアクションを実行するには **、Start-InformationBarrierPoliciesApplication コマンドレットを使用** します。

    構文: `Start-InformationBarrierPoliciesApplication`

    変更は、組織に対してユーザー別に適用されます。 組織が大規模な場合、このプロセスが完了するには 24 時間以上かかる場合があります。

## <a name="stop-a-policy-application"></a>ポリシー アプリケーションを停止する

情報バリア ポリシーの適用を開始した後、それらのポリシーの適用を停止する場合は、次の手順を使用します。 プロセスが開始するには、約 30 ~ 35 分かかります。

1. 最新の情報バリア ポリシー アプリケーションの状態を表示するには **、Get-InformationBarrierPoliciesApplicationStatus コマンドレットを使用** します。

    構文: `Get-InformationBarrierPoliciesApplicationStatus`

    アプリケーションの GUID に注意してください。

2. Identity パラメーター **と共に Stop-InformationBarrierPoliciesApplication** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> この例では、情報バリア ポリシーの適用を停止しています。 |

## <a name="resources"></a>リソース

- [情報バリアの概要を取得する](information-barriers.md)
- [情報バリアに対するポリシーを定義する](information-barriers-policies.md)
- [詳細については、Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [オンラインでの情報バリアの詳細SharePointする](/sharepoint/information-barriers)
- [詳細については、「情報バリア」を参照OneDrive](/onedrive/information-barriers)
- [情報障壁ポリシーの属性](information-barriers-attributes.md)
- [情報障壁のトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)