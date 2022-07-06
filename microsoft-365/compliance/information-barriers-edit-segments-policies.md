---
title: 情報バリア ポリシーを管理する
description: 情報バリアのポリシーを編集または削除する方法について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.openlocfilehash: a84b8e712de53b0abae81a05bbe1b2bef3237beb
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635307"
---
# <a name="manage-information-barriers-policies"></a>情報バリア ポリシーを管理する

[情報バリア (IB) ポリシーを定義](information-barriers-policies.md)した後、トラブルシューティングの一環として、または定期的なメンテナンスとして、それらのポリシーまたはユーザー セグメントに変更[を](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)加える必要がある場合があります。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

|**操作**|**説明**|
|:---------|:--------------|
| [ユーザー アカウントの属性を編集する](#edit-user-account-attributes) | セグメントの定義に使用できる属性を Azure Active Directory に入力します。 <br> ユーザーが必要なセグメントに含まれていない場合、ユーザーが含まれているセグメントを変更する場合、または異なる属性を使用してセグメントを定義する場合は、ユーザー アカウント属性を編集します。 |
| [セグメントを編集する](#edit-a-segment) | セグメントの定義方法を変更する場合は、セグメントを編集します。 <br> たとえば、 *最初に Department* を使用してセグメントを定義し、 *MemberOf* などの別の属性を使用する必要があるとします。 |
| [ポリシーを編集する](#edit-a-policy) | ポリシーの動作を変更する場合は、情報バリア ポリシーを編集します。<br> たとえば、2 つのセグメント間の通信をブロックする代わりに、特定のセグメント間でのみ通信を行えるようにすることができます。 |
| [ポリシーを非アクティブ状態に設定する](#set-a-policy-to-inactive-status) |ポリシーを変更する場合、またはポリシーを有効にしたくない場合は、ポリシーを非アクティブ状態に設定します。 |
| [ポリシーを削除する](#remove-a-policy) | 特定のポリシーを設定する必要がなくなった場合は、情報バリア ポリシーを削除します。 |
| [セグメントを削除する](#remove-a-segment) | 特定のセグメントが不要になった場合は、情報バリア セグメントを削除します。 |
| [ポリシーとセグメントを削除する](#remove-a-policy-and-segment) | 情報バリア ポリシーとセグメントを同時に削除します。 |
| [ポリシー アプリケーションを停止する](#stop-a-policy-application) | 情報バリア ポリシーを適用するプロセスを停止する場合は、このアクションを実行します。 <br> ポリシー アプリケーションの停止はすぐには行われず、既にユーザーに適用されているポリシーは元に戻しません。 |
| [情報バリアに対するポリシーを定義する](information-barriers-policies.md) | このようなポリシーがまだ設定されていない場合は、情報バリア ポリシーを定義し、特定のユーザー グループ間の通信を制限または制限する必要があります。 |
| [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting) | 情報バリアに関する予期しない問題が発生した場合は、この記事を参照してください。 |

>[!IMPORTANT]
>この記事で説明するタスクを実行するには、次のいずれかの適切なロールを割り当てる必要があります。<br>- Microsoft 365 Enterprise グローバル管理者<br>- グローバル管理者<br>- コンプライアンス管理者<br>- IB コンプライアンス管理 (これは新しいロールです!<br><br>情報バリアの前提条件の詳細については、「 [前提条件 (情報バリア ポリシーの場合)」](information-barriers-policies.md#step-1-make-sure-prerequisites-are-met)を参照してください。<br><br> [セキュリティ & コンプライアンス PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)してください。

## <a name="edit-user-account-attributes"></a>ユーザー アカウントの属性を編集する

この手順を使用して、ユーザーのセグメント化に使用される属性を編集します。 たとえば、Department 属性を使用していて、1 つ以上のユーザー アカウントに現在 Department の値が一覧表示されていない場合は、そのユーザー アカウントを編集して部署情報を含める必要があります。 ユーザー アカウント属性は、情報バリア ポリシーを割り当てることができるようにセグメントを定義するために使用されます。

1. 属性値や割り当てられたセグメントなど、特定のユーザー アカウントの詳細を表示するには、Identity パラメーターを使用して **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <br> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <br> (このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>` |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <br> この例では、Office 365の 2 つのユーザー アカウント (*meganb* for *Megan* と *alexw*) を参照します。 |

2. ユーザー アカウント プロファイルに対して編集する属性を決定します。 詳細については、「 [情報バリア ポリシーの属性」を](information-barriers-attributes.md)参照してください。

3. 前の手順で選択した属性の値を含めるには、1 つ以上のユーザー アカウントを編集します。 このアクションを実行するには、次のいずれかの手順を使用します。

    - 1 つのアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する」を](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)参照してください。

    - 複数のアカウントを編集する (または PowerShell を使用して 1 つのアカウントを編集する) 場合は、「[powerShell でユーザー アカウントのプロパティを構成するOffice 365](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)」を参照してください。

## <a name="edit-a-segment"></a>セグメントを編集する

この手順を使用して、ユーザー セグメントの定義を編集します。 たとえば、セグメントの名前や、セグメントに含まれるユーザーを特定するために使用されるフィルターを変更できます。

1. 既存のすべてのセグメントを表示するには、 **Get-OrganizationSegment** コマンドレットを使用します。

    構文： `Get-OrganizationSegment`

    セグメントの種類、UserGroupFilter 値、それを作成または最後に変更したユーザー、GUID など、各セグメントと詳細の一覧が表示されます。

    > [!TIP]
    > 後で参照できるように、セグメントの一覧を印刷または保存します。 たとえば、セグメントを編集する場合は、その名前または識別値を認識する必要があります (これは Identity パラメーターと共に使用されます)。

2. セグメントを編集するには、Identity パラメーターと関連する詳細を含む **Set-OrganizationSegment** コマンドレット **を** 使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <br> この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* でセグメントの部門名を *HRDept* に更新しました。 |

3. 組織のセグメントの編集が完了したら、情報バリア ポリシーを [定義](information-barriers-policies.md#step-3-create-ib-policies) または [編集](#edit-a-policy) できます。

## <a name="edit-a-policy"></a>ポリシーを編集する

1. 現在の情報バリア ポリシーの一覧を表示するには、 **Get-InformationBarrierPolicy** コマンドレットを使用します。

    構文： `Get-InformationBarrierPolicy`

    結果の一覧で、変更するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. **Id** パラメーターと共に **Set-InformationBarrierPolicy** コマンドレットを使用し、行う変更を指定します。

    例: *リサーチ* セグメントが *Sales* セグメントと *マーケティング* セグメントとの通信をブロックするようにポリシーが定義されたとします。 ポリシーは、次のコマンドレットを使用して定義されました。 `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    *リサーチ* セグメントのユーザーが *人事* セグメントのユーザーとのみ通信できるように変更したいとします。 この変更を行うには、次のコマンドレットを使用します。 `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    この例では、 *SegmentsBlocked を* *SegmentsAllowed* に変更し、 *HR* セグメントを指定しました。

3. ポリシーの編集が完了したら、必ず変更を適用してください。 ( [「情報バリア ポリシーを適用する](information-barriers-policies.md#step-4-apply-ib-policies)」を参照してください)。

## <a name="set-a-policy-to-inactive-status"></a>ポリシーを非アクティブ状態に設定する

1. 現在の情報バリア ポリシーの一覧を表示するには、 **Get-InformationBarrierPolicy** コマンドレットを使用します。

    構文： `Get-InformationBarrierPolicy`

    結果の一覧で、変更 (または削除) するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. ポリシーの状態を非アクティブに設定するには、*Id* パラメーターと *State* パラメーターを *非アクティブ* に設定した **Set-InformationBarrierPolicy** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <br> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247* を持つ情報バリア ポリシーが非アクティブ状態に設定されています。 |

3. 変更を適用するには、 **Start-InformationBarrierPoliciesApplication コマンドレットを** 使用します。

    構文： `Start-InformationBarrierPoliciesApplication`

    変更は、組織に対してユーザーごとに適用されます。 組織が大規模な場合、このプロセスが完了するまでに 24 時間以上かかる場合があります。 一般的なガイドラインとして、5,000 個のユーザー アカウントを処理するのに約 1 時間かかります。

4. この時点で、1 つ以上の情報バリア ポリシーが非アクティブ状態に設定されます。 ここから、次のいずれかの操作を実行できます。

    - そのままにする (非アクティブ状態に設定されたポリシーは、ユーザーには影響しません)
    - [ポリシーを編集する](#edit-a-policy) 
    - [ポリシーを削除する](#remove-a-policy)

## <a name="remove-a-policy"></a>ポリシーを削除する

1. 現在の情報バリア ポリシーの一覧を表示するには、 **Get-InformationBarrierPolicy** コマンドレットを使用します。

    構文： `Get-InformationBarrierPolicy`

    結果の一覧で、削除するポリシーを特定します。 ポリシーの GUID と名前をメモします。 

2. ポリシーが非アクティブ状態に設定されていることを確認します。 ポリシーの状態を非アクティブに設定するには、Id パラメーターと State パラメーターを非アクティブに設定したSet-InformationBarrierPolicy コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive`  | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <br> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247* を非アクティブ状態にする情報バリア ポリシーを設定します。 |

3. ポリシーに変更を適用するには、 **Start-InformationBarrierPoliciesApplication コマンドレットを** 使用します。

    構文： `Start-InformationBarrierPoliciesApplication`

    変更は、組織に対してユーザーごとに適用されます。 組織が大規模な場合、このプロセスが完了するまでに 24 時間以上かかる場合があります。 一般的なガイドラインとして、5,000 個のユーザー アカウントを処理するのに約 1 時間かかります。

4. Identity パラメーターを使用して **Remove-InformationBarrierPolicy** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <br> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* を持つポリシーを削除しています。 |

    メッセージが表示されたら、変更を確認します。

## <a name="remove-a-segment"></a>セグメントを削除する

1. 既存のすべてのセグメントを表示するには、 **Get-OrganizationSegment** コマンドレットを使用します。

    構文： `Get-OrganizationSegment`

    セグメントの種類、UserGroupFilter 値、それを作成または最後に変更したユーザー、GUID など、各セグメントと詳細の一覧が表示されます。

    >[!TIP]
    >後で参照できるように、セグメントの一覧を印刷または保存します。 たとえば、セグメントを編集する場合は、その名前または識別値を認識する必要があります (これは Identity パラメーターと共に使用されます)。

2. 削除するセグメントを特定し、セグメントに関連付けられている IB ポリシーが削除されていることを確認します。 詳細については、 [ポリシーの削除](#remove-a-policy) 手順を参照してください。

3. 削除されるセグメントを編集して、そのセグメントに対するユーザーの関係を削除します。 このアクションにより、セグメント定義が更新され、セグメントからすべてのユーザーが削除されます。 UserGroupFilter パラメーターを使用して、削除する前にセグメントからユーザーの関連付けを解除します。

    セグメントを編集するには、Identity パラメーターと関連する詳細を含む **Set-OrganizationSegment** コマンドレット *を* 使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` | `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'FakeDept'"` <br> この例では、GUID c96e0837-c232-4a8a-841e-ef45787d8fcd を持つセグメントについて、セグメントからユーザーを削除するために部門名を *FakeDept* として定義しました。 この例では *Department* 属性を使用しますが、必要に応じて他の属性を使用できます。 この例では *FakeDept* を使用しています。これは存在せず、ユーザーが含まれていないのは確実であるためです。 |

4. 変更を適用するには、 **Start-InformationBarrierPoliciesApplication コマンドレットを** 使用します。

    構文： `Start-InformationBarrierPoliciesApplication -CleanupGroupSegmentLink`

    >[!NOTE]
    >*CleanupGroupSegmentLink* 属性は、ユーザーの関連付けを持たないセグメントとのグループ関連付けを削除します。

    変更は、組織に対してユーザーごとに適用されます。 組織が大規模な場合、このプロセスが完了するまでに 24 時間以上かかる場合があります。 一般的なガイドラインとして、5,000 個のユーザー アカウントを処理するのに約 1 時間かかります。

5. セグメントを削除するには、Identity パラメーターと関連する詳細を含む **Remove-OrganizationSegment** コマンドレット *を* 使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Remove-OrganizationSegment -Identity GUID` | `Remove-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <br> この例では、GUID c96e0837-c232-4a8a-841e-ef45787d8fcd を持つセグメントが削除されました。 |

## <a name="remove-a-policy-and-segment"></a>ポリシーとセグメントを削除する

1. 現在の情報バリア ポリシーの一覧を表示するには、 **Get-InformationBarrierPolicy** コマンドレットを使用します。

    構文： `Get-InformationBarrierPolicy`

    結果の一覧で、削除するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. 既存のすべてのセグメントを表示するには、 **Get-OrganizationSegment** コマンドレットを使用します。

    構文： `Get-OrganizationSegment`

    セグメントの種類、 *UserGroupFilter* パラメーター値、それを作成または最後に変更したユーザー、GUID など、各セグメントと詳細の一覧が表示されます。

    >[!TIP]
    >後で参照できるように、セグメントの一覧を印刷または保存します。 たとえば、セグメントを編集する場合は、その名前または識別値を認識する必要があります (これは Identity パラメーターと共に使用されます)。

3. 削除するポリシーの状態を非アクティブに設定するには、*Id* パラメーターと *State* パラメーターを非アクティブに設定した **Set-InformationBarrierPolicy** コマンドレットを使用 *します*。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Inactive` <br> この例では、GUID 43c37853-ea10-4b90-a23d-ab8c93772471 を非アクティブ状態にする情報バリア ポリシーを設定します。 |

4. 削除されるセグメントを編集して、そのセグメントに対するユーザーの関係を削除します。 このアクションにより、セグメント定義が更新され、セグメントからすべてのユーザーが削除されます。 *UserGroupFilter* パラメーターを使用して、削除する前にセグメントからユーザーの関連付けを解除します。

    セグメントを編集するには、Identity パラメーターと関連する詳細を含む **Set-OrganizationSegment** コマンドレット *を* 使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` | `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'FakeDept'"` <br> この例では、GUID c96e0837-c232-4a8a-841e-ef45787d8fcd を持つセグメントについて、部門名を *FakeDept* に更新してセグメントからユーザーを削除しました。 この例では *Department* 属性を使用しますが、必要に応じて他の属性を使用できます。 この例では *FakeDept* を使用しています。これは存在せず、ユーザーが含まれていないのは確実であるためです。 |

5. 変更を適用するには、 **Start-InformationBarrierPoliciesApplication コマンドレットを** 使用します。

    構文： `Start-InformationBarrierPoliciesApplication -CleanupGroupSegmentLink`

    >[!NOTE]
    >*CleanupGroupSegmentLink* 属性は、ユーザーの関連付けを持たないセグメントとのグループ関連付けを削除します。

    変更は、組織に対してユーザーごとに適用されます。 組織が大規模な場合、このプロセスが完了するまでに 24 時間以上かかる場合があります。 一般的なガイドラインとして、5,000 個のユーザー アカウントを処理するのに約 1 時間かかります。

6. *Identity* パラメーターを使用して **Remove-InformationBarrierPolicy** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <br> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* を持つポリシーが削除されます。 |

    メッセージが表示されたら、変更を確認します。

7. セグメントを削除するには、Identity パラメーターと関連する詳細を含む **Remove-OrganizationSegment** コマンドレット *を* 使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Remove-OrganizationSegment -Identity GUID` | `Remove-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <br> この例では、GUID c96e0837-c232-4a8a-841e-ef45787d8fcd を持つセグメントが削除されました。 |

## <a name="stop-a-policy-application"></a>ポリシー アプリケーションを停止する

情報バリア ポリシーの適用を開始したら、それらのポリシーの適用を停止する場合は、次の手順に従います。 プロセスを開始するには、約 30 ~ 35 分かかります。

1. 最新の情報バリア ポリシー アプリケーションの状態を表示するには、 **Get-InformationBarrierPoliciesApplicationStatus** コマンドレットを使用します。

    構文： `Get-InformationBarrierPoliciesApplicationStatus`

    アプリケーションの GUID に注意してください。

2. Id パラメーターを使用して **Stop-InformationBarrierPoliciesApplication** コマンドレットを使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> この例では、情報バリア ポリシーの適用を停止しています。 |

## <a name="resources"></a>リソース

- [情報バリアの概要を確認する](information-barriers.md)
- [情報バリアに対するポリシーを定義する](information-barriers-policies.md)
- [Microsoft Teams の情報バリアの詳細を確認する](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDrive の情報バリアの詳細を確認する](/onedrive/information-barriers)
- [IB ポリシーの属性](information-barriers-attributes.md)
- [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
