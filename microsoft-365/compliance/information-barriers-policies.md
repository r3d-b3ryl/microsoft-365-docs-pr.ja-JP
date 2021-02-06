---
title: 情報バリア ポリシーの定義
description: Microsoft Teams で情報バリアのポリシーを定義する方法について説明します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09e680d2bcf8f1e0fd5237adbf640349741c26fd
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126586"
---
# <a name="define-information-barrier-policies"></a>情報バリア ポリシーの定義

情報バリアを使用すると、ユーザーの特定のセグメントが互いに通信し合うのを防ぐポリシーを定義したり、特定のセグメントが特定の他のセグメントとのみ通信したりするように設計されたポリシーを定義できます。 情報バリア ポリシーは、組織が関連する業界標準と規制への準拠を維持し、潜在的な利益の競合を回避するのに役立ちます。 詳細については、「情報バリア [」を参照してください](information-barriers.md)。

この記事では、情報バリア ポリシーを計画、定義、実装、および管理する方法について説明します。 複数の手順が必要であり、作業フローは複数の部分に分かれています。 情報バリア ポリシーの定義[](#prerequisites)(または編集) を開始する前に、前提条件とプロセス全体を必ずお読みください。

> [!TIP]
> この記事には、シナリオ [の例と](#example-contosos-departments-segments-and-policies) 、情報バリア ポリシーの計画と定義に役立つダウンロード可能な [Excel](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) ブックが含まれています。

## <a name="concepts-of-information-barrier-policies"></a>情報バリア ポリシーの概念

情報バリアのポリシーを定義する場合は、ユーザー アカウント属性、セグメント、"ブロック" ポリシーや "許可" ポリシー、およびポリシー アプリケーションを使用します。

- ユーザー アカウント属性は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、およびその他のジョブ プロファイルの詳細を含めることができます。 
- セグメントは、選択したユーザー アカウント属性を使用してセキュリティ & コンプライアンス センター **で定義されているユーザーのセットです**。 ([サポートされる属性の一覧](information-barriers-attributes.md)を参照してください。)
- 情報バリア ポリシーは、通信の制限値または制限を決定します。 情報バリア ポリシーを定義する際は、次の 2 種類のポリシーから選択します。
    - "ブロック" ポリシーは、あるセグメントが別のセグメントと通信を行うのを防止します。
    - "許可" ポリシーでは、1 つのセグメントが他の特定のセグメントとのみ通信できます。
- ポリシーの適用は、すべての情報バリア ポリシーが定義された後に実行され、組織に適用する準備が整います。

## <a name="the-work-flow-at-a-glance"></a>ワークフローの概要

|**フェーズ**|**内容**|
|:--------|:------------------|
| [前提条件が満たされていることを確認する](#prerequisites) | - 必要なライセンスと [アクセス許可を持っている](information-barriers.md#required-licenses-and-permissions)<br/>- セグメント化されたユーザーのデータがディレクトリに含まれるか確認する<br/>- Microsoft Teams のスコープ指定ディレクトリ検索を有効にする<br/>- 監査ログが有効になっていることを確認する<br/>- Exchange アドレス帳ポリシーが適用でいなかっているのを確認する<br/>- PowerShell を使用する (例を示します)<br/>- Microsoft Teams に管理者の同意を提供する (手順が含まれています) |
| [パート 1: 組織内のユーザーをセグメント化する](#part-1-segment-users) | - 必要なポリシーを決定する<br/>- 定義するセグメントの一覧を作成する<br/>- 使用する属性を特定する<br/>- ポリシー フィルターの観点からセグメントを定義する |
| [パート 2: 情報バリア ポリシーを定義する](#part-2-define-information-barrier-policies) | - ポリシーを定義する (まだ適用しない)<br/>- 2 つの種類から選択する (ブロックまたは許可) |
| [パート 3: 情報バリア ポリシーを適用する](#part-3-apply-information-barrier-policies) | - ポリシーをアクティブな状態に設定する<br/>- ポリシー アプリケーションを実行する<br/>- ポリシーの状態を表示する |
| (必要に応じて) [セグメントまたはポリシーを編集する](information-barriers-edit-segments-policies.md) | - セグメントを編集する<br/>- ポリシーを編集または削除する<br/>- ポリシー アプリケーションを再実行する<br/>- ポリシーの状態を表示する |
| (必要に応じて) [トラブルシューティング](information-barriers-troubleshooting.md)| - 想定通り動作しない場合にアクションを実行する|

## <a name="prerequisites"></a>前提条件

必要なライセンス [とアクセス許可に加](information-barriers.md#required-licenses-and-permissions)えて、次の要件を満たしていることを確認します。

- ディレクトリ データ - 組織の構造がディレクトリ データに反映されます。 このアクションを実行するには、グループ メンバーシップ、部門名などのユーザー アカウント属性が Azure Active Directory (または Exchange Online) に正しく設定されていることを確認します。 詳細については、次のリソースを参照してください。
  - [情報障壁ポリシーの属性](information-barriers-attributes.md)
  - [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell でユーザー アカウント プロパティを構成する](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- スコープ指定されたディレクトリ検索 - 組織の最初の情報バリア ポリシーを定義する前に、Microsoft Teams でスコープ指定されたディレクトリ検索を有効 [にする必要があります](/MicrosoftTeams/teams-scoped-directory-search)。 情報バリア ポリシーを設定または定義する前に、スコープ指定されたディレクトリ検索を有効にしてから少なくとも 24 時間待ちます。

- EXO ライセンス - ターゲット ユーザーに EXO ライセンスが割り当てられている場合にのみ、IBS ポリシーが機能します。

- 監査ログ - ポリシー アプリケーションの状態を参照するには、監査ログを有効にする必要があります。 セグメントまたはポリシーの定義を開始する前に、監査を有効にすることをお勧めします。 詳細については、「監査ログ [検索を有効またはオフにする」を参照してください](turn-audit-log-search-on-or-off.md)。

- アドレス帳ポリシーなし - 情報バリア ポリシーを定義して適用する前に、Exchange アドレス帳ポリシーが適用されないか確認してください。 情報バリアはアドレス帳ポリシーに基づいていますが、2 種類のポリシーには互換性がありません。 このようなポリシーがある場合は、まずアドレス帳 [ポリシーを削除](/exchange/address-books/address-book-policies/remove-an-address-book-policy) してください。 情報バリア ポリシーを有効にし、階層型アドレス帳を有効にすると、情報バリア セグメントに含まれていないすべてのユーザーに、Exchange [](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) Online の階層型アドレス帳が表示されます。

- PowerShell - 現在、情報バリア ポリシーは、PowerShell コマンドレットを使用して Office 365 セキュリティ/コンプライアンス センターで&管理されています。 この記事ではいくつかの例を示しますが、PowerShell のコマンドレットとパラメーターについて理解している必要があります。 Azure PowerShell モジュールも必要です。
    - [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)
    - [Azure PowerShell モジュールをインストールする](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Microsoft Teams の情報障壁に対する管理者の同意 - ポリシーが適用されている場合、情報バリアによって、想定されていないチャット セッションからユーザーが削除される可能性があります。 この構成は、組織がポリシーと規制に準拠し続けるのに役立ちます。 Microsoft Teams で情報バリア ポリシーが期待通り動作するには、次の手順を使用します。

   1. 次の PowerShell コマンドレットを実行します。

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. メッセージが表示されたら、365 の学校または学校のアカウントをOfficeします。

   3. In the **Permissions requested** dialog box, review the information, and then choose **Accept**.

すべての前提条件が満たされた場合は、次のセクションに進みます。

> [!TIP]
> 計画を準備するために、この記事にはシナリオの例が含まれています。 [Contoso 社の部署、セグメント、およびポリシーを参照してください](#example-contosos-departments-segments-and-policies)。<p>また、ダウンロード可能な Excel ブックを使用して、セグメントとポリシーの計画と定義 (および PowerShell コマンドレットの作成) を行うのに役立ちます。 [ブックを取得します](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。

## <a name="part-1-segment-users"></a>パート 1: ユーザーをセグメント化する

このフェーズでは、必要な情報バリア ポリシーを決定し、定義するセグメントの一覧を作成してから、セグメントを定義します。

### <a name="determine-what-policies-are-needed"></a>必要なポリシーを決定する

法律や業界の規制を考慮すると、組織内の情報障壁ポリシーを必要とするグループは誰ですか? リストを作成します。 他のグループとの通信を妨げる必要があるグループはありますか? 他の 1 つのグループまたは 2 つのグループとの通信のみを許可する必要があるグループはありますか? 必要なポリシーを次の 2 つのグループの 1 つに属すると考えてみください。

- "ブロック" ポリシーは、あるグループが別のグループと通信を行うのを防止します。
- "許可" ポリシーでは、グループが他の特定の特定のグループとのみ通信できます。

グループとポリシーの初期リストがある場合は、必要なセグメントの特定に進みます。

### <a name="identify-segments"></a>セグメントを特定する

ポリシーの初期リストに加えて、組織のセグメントの一覧を作成します。 情報バリア ポリシーに含めるユーザーは、セグメントに属している必要があります。 ユーザーが 1 つのセグメントにのみ含め、セグメントを慎重に計画します。 各セグメントに適用できる情報バリア ポリシーは 1 つのみです。

> [!IMPORTANT]
> ユーザーは 1 つのセグメントにのみ含めできます。

セグメントの定義に使用する組織のディレクトリ データ内の属性を決定します。 *Department、MemberOf、または* サポートされている任意の属性を使用できます。  ユーザーに対して選択する属性に値が含まれます。 [情報バリアについてサポートされている属性の一覧を参照してください](information-barriers-attributes.md)。

> [!IMPORTANT]
> **次のセクションに進む前に、** セグメントの定義に使用できる属性の値がディレクトリ データに含まれています。 ディレクトリ データに使用する属性の値が設定されていない場合は、情報バリアに進む前に、その情報を含むユーザー アカウントを更新する必要があります。 このヘルプについては、次のリソースを参照してください。<br/>- [Office 365 PowerShell を使用してユーザー アカウントのプロパティを構成する](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell を使用してセグメントを定義する

セグメントを定義しても、ユーザーには影響を与え得ない。情報バリア ポリシーを定義して適用する段階を設定します。

1. **New-OrganizationSegment** コマンドレットは、使用する属性に対応する **UserGroupFilter** [パラメーターと一](information-barriers-attributes.md)緒に使用します。

    |**構文**|**例**|
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>この例では *、HR* と呼ばれるセグメントを *、Department* 属性の値である HR を使用して *定義* します。 コマンドレット **の -eq** 部分は"等しい" を参照します。 (または、-ne を **使用** して "等しくない" ことを意味します。 セグメント [定義での "等しい"](#using-equals-and-not-equals-in-segment-definitions)と "等しくない" の使用を参照してください)。 |

    各コマンドレットを実行すると、新しいセグメントに関する詳細の一覧が表示されます。 詳細には、セグメントの種類、セグメントを作成または最後に変更したユーザーなどです。 

2. 定義するセグメントごとにこのプロセスを繰り返します。

    > [!IMPORTANT]
    > **セグメントが重ならないようにしてください**。 情報バリアの影響を受ける各ユーザーは、1 つのセグメント (および 1 つのセグメントのみ) に属している必要があります。 2 つ以上のセグメントに属するユーザーはいけな。 (例 [: この記事で Contoso 社が定義したセグメント](#contosos-defined-segments) を参照してください)。

セグメントを定義した後、情報バリア ポリシーの [定義に進みます](#part-2-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>セグメント定義で "equals" と "not equals" を使用する

次の例では、"Department equals HR" のようなセグメントを定義しています。 

|**例**|**注**|
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | この例では、セグメント定義に -eq として示される "equals" パラメーター **が含まれています**。 |

次の表に示すように **、-ne** という "等しくない" パラメーターを使用してセグメントを定義することもできます。

|**構文**|**例**|
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | この例では、営業ではないすべてのユーザーを含む *NotSales* というセグメントを定義 *しました*。 コマンドレット **の -ne** 部分は"等しくない" を参照します。 |

"equals" または "not equals" を使用してセグメントを定義する以外に、"equals" パラメーターと "not equals" パラメーターの両方を使用してセグメントを定義できます。 論理 AND 演算子と OR 演算子を使用して、複雑な *グループ フィルター**を定義* することもできます。

|**構文**|**例**|
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | この例では *、LocalFTE* というセグメントを定義しました。このセグメントには、ローカルに配置され、位置が Temporary としてリストされていないユーザーが含 *まれます*。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| この例では、セグメント 1 のメンバーではなく、group1@contoso.com のメンバーであるユーザーを含む *Segment1* というセグメントをgroup3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | この例では *、Segment2* というセグメントを定義しました。このセグメントには、ユーザーのメンバーではなく、group2@contoso.com のメンバーであるユーザーがgroup3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| この例では *、Segment1and2* というセグメントを定義しました。このセグメントには、group1@contoso.com と group2@contoso.com のメンバーを含め、group3@contoso.com。 |

> [!TIP]
> 可能であれば、"-eq" または "-ne" を含むセグメント定義を使用します。 複雑なセグメント定義を定義しない。

## <a name="part-2-define-information-barrier-policies"></a>パート 2: 情報バリア ポリシーを定義する

特定のセグメント間の通信を防止するか、通信を特定のセグメントに制限する必要があるかどうかを決定します。 組織が法律や業界の要件に準拠していることを確認するために、ポリシーの最小数を使用するのが理想的です。

ユーザー セグメントの一覧と、定義する情報バリア ポリシーを使用して、シナリオを選択し、手順に従います。

- [シナリオ 1: セグメント間の通信をブロックする](#scenario-1-block-communications-between-segments)
- [シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **ポリシーを定義する場合は、1 つのセグメントに複数のポリシーを割り当てないでください**。 たとえば、Sales というセグメントに対して 1つのポリシーを定義する場合は、Sales に追加のポリシーを定義 *しない必要があります*。<p> さらに、情報バリア ポリシーを定義する場合は、ポリシーを適用する準備が整うまで、それらのポリシーを非アクティブな状態に設定してください。 ポリシーを定義 (または編集) しても、ポリシーがアクティブな状態に設定され、適用されるまでは、ユーザーに影響を与える必要があります。

(例 [: この記事の Contoso 社の情報バリア ポリシー](#contosos-information-barrier-policies) を参照してください)。

### <a name="scenario-1-block-communications-between-segments"></a>シナリオ 1: セグメント間の通信をブロックする

セグメント間の通信をブロックする場合は、方向ごとに 1 つのポリシーを定義します。 各ポリシーは、通信を一方的にのみブロックします。

たとえば、セグメント A とセグメント B の間の通信をブロックするとします。この場合は、セグメント A とセグメント B との通信を妨げる 1 つのポリシーを定義し、セグメント B とセグメント A との通信を防止する 2 つ目のポリシーを定義します。

1. 最初のブロック ポリシーを定義するには、SegmentsBlocked パラメーターを指定して **New-InformationBarrierPolicy** **コマンドレットを使用** します。

    |**構文** |**例**| |**--------|:----------| |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、Sales というセグメントに *Sales-Research* というポリシーを定義 *しました*。 アクティブで適用されている場合、このポリシーは *、Sales* のユーザーが Research というセグメント内のユーザーと通信を行うのを防止 *します*。 |

2. 2 番目のブロック セグメントを定義するには **、New-InformationBarrierPolicy** コマンドレットを **SegmentsBlocked** パラメーターと一緒に使用し、今回はセグメントを逆に設定します。

    |**例**|**注**|
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | この例では *、Research-Sales* というポリシーを定義して *、Research* と Sales との通信を防 *ぎたとします*。 |

3. 次のいずれかの操作に進みます。

   - (必要な場合) [セグメントが他の 1 つのセグメントとのみ通信できるポリシーを定義する](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーの適用](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする

1. 1 つのセグメントが他の 1 つのセグメントとのみ通信するには **、New-InformationBarrierPolicy** コマンドレットを **SegmentsAllowed** パラメーターと一緒に使用します。

    |**構文**|**例**|
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> この例では、Manufacturing というセグメントに *Manufacturing-HR* というポリシーを定義 *しました*。 アクティブで適用されている場合、このポリシーにより、 *製造* 部門のユーザーは HR というセグメント内のユーザーとのみ通信 *できます*。 (この場合、 *人事* 部ではないユーザーと製造は通信 *できません*。 |

    **必要に応じて、次の例に示すように、このコマンドレットで複数のセグメントを指定できます。**

    |**構文**|**例**|
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> この例では、Research セグメントと HR および *Manufacturing* のみとの通信を許可 *するポリシー* を定義 *しました*。 |

    定義するポリシーごとにこの手順を繰り返し、特定のセグメントが他の特定のセグメントのみと通信することを許可します。

2. 次のいずれかの操作に進みます。

   - (必要な場合) [セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments) 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーの適用](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>パート 3: 情報バリア ポリシーを適用する

情報バリア ポリシーは、アクティブな状態に設定してからポリシーを適用するまでは有効ではありません。

1. **Get-InformationBarrierPolicy** コマンドレットを使用して、定義されているポリシーの一覧を表示します。 各ポリシーの状態と ID (GUID) をメモします。

    構文: `Get-InformationBarrierPolicy`

2. ポリシーをアクティブな状態に設定するには、Identity パラメーターを指定して **Set-InformationBarrierPolicy** コマンドレットを使用し **、State** パラメーターを Active に設定 **します**。  

    |**構文**|**例**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> この例では、GUID *が 43c37853-ea10-4b90-a23d-ab8c93772471* の情報バリア ポリシーをアクティブな状態に設定します。 |

    各ポリシーに応じて、この手順を繰り返します。

3. 情報バリア ポリシーをアクティブな状態に設定し終わったら、セキュリティ センター コンプライアンス センターで **Start-InformationBarrierPoliciesApplication** コマンドレット&使用します。

    構文: `Start-InformationBarrierPoliciesApplication`

    実行後、 `Start-InformationBarrierPoliciesApplication` システムがポリシーの適用を開始するために 30 分かかります。 システムは、ユーザー別にポリシーを適用します。 システムは、1 時間あたり約 5,000 のユーザー アカウントを処理します。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示する

PowerShell を使用すると、次の表に示すユーザー アカウント、セグメント、ポリシー、およびポリシー アプリケーションの状態を表示できます。

|**この情報を表示するには**|**このアクションを実行する**|
|:---------------|:----------|
| ユーザー アカウント | Identity パラメーター **を指定して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 <p> 構文: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p> 例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、365 年 365 日に Office 2 つのユーザー アカウント *(megan* の場合は *meganb、Alex* の場合は *alexw)* を参照 *します*。 <p> (このコマンドレットは、1 人のユーザーに対して使用することもできます `Get-InformationBarrierRecipientStatus -Identity <value>` 。 <p> このコマンドレットは、属性値や適用されている情報バリア ポリシーなど、ユーザーに関する情報を返します。|
| セグメント | **Get-OrganizationSegment コマンドレットを使用** します。<p> 構文: `Get-OrganizationSegment` <p> このコマンドレットは、組織に定義されている全セグメントの一覧を表示します。 |
| 情報バリア ポリシー | **Get-InformationBarrierPolicy コマンドレットを使用** します。 <p> 構文: `Get-InformationBarrierPolicy` <p> このコマンドレットは、定義された情報バリア ポリシーとその状態の一覧を表示します。 |
| 最新の情報バリア ポリシー アプリケーション | **Get-InformationBarrierPoliciesApplicationStatus コマンドレットを使用** します。 <p> 構文: `Get-InformationBarrierPoliciesApplicationStatus`<p> このコマンドレットは、ポリシー アプリケーションが完了した、失敗した、または進行中かどうかに関する情報を表示します。 |
| すべての情報バリア ポリシー アプリケーション|`Get-InformationBarrierPoliciesApplicationStatus -All` を使う<p> このコマンドレットは、ポリシー アプリケーションが完了した、失敗した、または進行中かどうかに関する情報を表示します。|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>ポリシーを削除または変更する必要がある場合は、

情報バリア ポリシーの管理に役立つリソースを利用できます。

- 情報バリアに問題がある場合は、「情報バリアのトラブルシューティング [」を参照してください](information-barriers-troubleshooting.md)。
- ポリシーの適用を停止するには、「ポリシー アプリケーションを停止 [する」を参照してください](information-barriers-edit-segments-policies.md#stop-a-policy-application)。
- 情報バリア ポリシーを削除するには、「ポリシーを削除 [する」を参照してください](information-barriers-edit-segments-policies.md#remove-a-policy)。
- セグメントまたはポリシーを変更するには、「情報バリア ポリシーを編集 [(または削除) する」を参照してください](information-barriers-edit-segments-policies.md)。

## <a name="example-contosos-departments-segments-and-policies"></a>例: Contoso 社の部署、セグメント、およびポリシー

組織がセグメントおよびポリシーを定義する方法については、次の例を参照してください。

### <a name="contosos-departments-and-plan"></a>Contoso の部門とプラン

Contoso には、人事、営業、マーケティング、リサーチ、製造の5つの部門があります。 業界の規制に準拠し続けするために、一部の部門のユーザーは、次の表に示す他の部署と通信する必要があります。

|**セグメント**|**に連絡できます**|**に連絡できません**|
|:----------|:--------------|:-----------------|
| HR | すべてのユーザー | (制限なし) |
| 営業 | 人事、マーケティング、製造 | 研究 |
| マーケティング | すべてのユーザー | (制限なし) |
| リサーチ | 人事、マーケティング、製造 | 営業 |
| 製造 | 人事、マーケティング | 人事またはマーケティング以外のユーザー |

この構造に関して、Contoso 社の計画には次の 3 つの情報バリア ポリシーが含まれています。

1. Sales が Research と通信し合うのを防ぐために設計されたポリシー (および Research と Sales との通信を防止する別のポリシー)。
2. 製造が人事およびマーケティング部門とのみ通信するように設計されたポリシー。

このシナリオでは、人事またはマーケティングのポリシーを定義する必要はありません。

### <a name="contosos-defined-segments"></a>Contoso の定義済みセグメント

Contoso 社は、次のように、Azure Active Directory の Department 属性を使用してセグメントを定義します。

|**Department**|**セグメント定義**|
|:-------------|:---------------------|
| 人事 | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| 営業 | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| マーケティング | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| リサーチ | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| 製造 | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

定義されたセグメントを使用して、Contoso がポリシーを定義します。

### <a name="contosos-information-barrier-policies"></a>Contoso の情報バリアポリシー

Contoso 社では、次の表に示す 3 つのポリシーを定義します。

|**Policy**|**ポリシー定義**|
|:---------|:--------------------|
| **ポリシー 1: 営業部門がリサーチ部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、情報バリアポリシーは、*営業-リサーチ* と呼ばれています。 このポリシーが適応されると、営業セグメント内のユーザーがリサーチセグメント内のユーザーと通信できなくなります。 このポリシーは一方通行のポリシーです。Research が Sales と通信できない可能性があります。 そのため、ポリシー2が必要です。 |
| **ポリシー 2: リサーチ部門が営業部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> この例では、情報バリアポリシーは、*リサーチ-営業* と呼ばれています。 このポリシーが適応されると、リサーチセグメント内のユーザーが、営業セグメント内のユーザーと通信できなくなります。 |
| **ポリシー 3: 製造が人事およびマーケティング部門とのみ通信を許可する** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> この場合、情報バリアポリシーは、*製造-人事マーケティング* と呼ばれています。 このポリシーが適応されると、製造部門は人事およびマーケティング部門とだけ通信を行えます。 人事およびマーケティングは、他のセグメントとの通信を制限されません。 |

セグメントとポリシーが定義されている状態で、Contoso は **Start-InformationBarrierPoliciesApplication** コマンドレットを実行してポリシーを適用します。

コマンドレットが終了すると、Contoso は法律および業界の要件に準拠します。

## <a name="resources"></a>リソース

- [情報バリアの概要を取得する](information-barriers.md)
- [Microsoft Teams の情報障壁の詳細](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDrive の情報バリアの詳細](/onedrive/information-barriers)
