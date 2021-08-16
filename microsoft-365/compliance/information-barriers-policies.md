---
title: 情報バリア ポリシーの定義
description: 情報バリアのポリシーを定義する方法については、Microsoft Teams。
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
ms.openlocfilehash: aec023a2d60d188900cf6afcc97f0f03cfc0aec4ea6860abb2782f7fd554342d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53905561"
---
# <a name="define-information-barrier-policies"></a>情報バリア ポリシーの定義

情報バリアを使用すると、特定のセグメントのユーザーが相互に通信したり、特定のセグメントが特定のセグメントとのみ通信したりするように設計されたポリシーを定義できます。 情報バリア ポリシーは、組織が関連する業界標準と規制への準拠を維持し、潜在的な利益相反を回避するのに役立ちます。 詳細については、「情報バリア [」を参照してください](information-barriers.md)。

この記事では、情報バリア ポリシーを計画、定義、実装、および管理する方法について説明します。 いくつかの手順が関係し、作業フローはいくつかの部分に分かれています。 情報バリア ポリシーの定義[](#prerequisites)(または編集) を開始する前に、前提条件とプロセス全体を必ずお読みください。

> [!TIP]
> この記事には、シナリオ[の例](#example-contosos-departments-segments-and-policies)と、情報バリア ポリシーを計画[Excel](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)定義するためのダウンロード可能なブックが含まれています。

## <a name="concepts-of-information-barrier-policies"></a>情報バリア ポリシーの概念

情報バリアのポリシーを定義する場合は、ユーザー アカウントの属性、セグメント、"ブロック" ポリシー、または "許可" ポリシー、およびポリシー アプリケーションを使用します。

- ユーザー アカウント属性は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、およびその他のジョブ プロファイルの詳細を含めることができます。 
- セグメントは、選択したユーザー アカウント属性を使用して、セキュリティ &コンプライアンス センターで定義されている **ユーザーのセットです**。 ([サポートされる属性の一覧](information-barriers-attributes.md)を参照してください。)
- 情報バリア ポリシーは、通信の制限値または制限を決定します。 情報バリア ポリシーを定義する際は、次の 2 種類のポリシーから選択します。
  - "ブロック" ポリシーは、あるセグメントが別のセグメントと通信を妨げる。
  - "許可" ポリシーでは、1 つのセグメントが特定の他のセグメントとのみ通信できます。
- ポリシーの適用は、すべての情報バリア ポリシーが定義された後に実行され、組織に適用する準備が整います。

## <a name="the-work-flow-at-a-glance"></a>ワークフローの概要

| フェーズ | 内容 |
|:--------|:------------------|
| [前提条件が満たされていることを確認する](#prerequisites) | - 必要なライセンスとアクセス [許可を持っているか確認する](information-barriers.md#required-licenses-and-permissions)<br/>- ディレクトリにセグメント化ユーザーのデータが含まれるか確認する<br/>- ディレクトリのスコープ検索を有効Microsoft Teams<br/>- 監査ログが有効になっていることを確認する<br/>- アドレス帳ポリシー Exchangeが設定されている必要はありません<br/>- PowerShell を使用する (例を示します)<br/>- 管理者の同意をMicrosoft Teamsする (手順が含まれています) |
| [パート 1: 組織内のユーザーをセグメント化する](#part-1-segment-users) | - 必要なポリシーを決定する<br/>- 定義するセグメントの一覧を作成する<br/>- 使用する属性を特定する<br/>- ポリシー フィルターの観点からセグメントを定義する |
| [パート 2: 情報バリア ポリシーの定義](#part-2-define-information-barrier-policies) | - ポリシーを定義する (まだ適用しない)<br/>- 2 つの種類から選択します (ブロックまたは許可) |
| [パート 3: 情報バリア ポリシーの適用](#part-3-apply-information-barrier-policies) | - ポリシーをアクティブな状態に設定する<br/>- ポリシー アプリケーションを実行する<br/>- ポリシーの状態を表示する |
| (必要に応じて) [セグメントまたはポリシーの編集](information-barriers-edit-segments-policies.md) | - セグメントを編集する<br/>- ポリシーを編集または削除する<br/>- ポリシー アプリケーションを再実行する<br/>- ポリシーの状態を表示する |
| (必要に応じて) [トラブルシューティング](information-barriers-troubleshooting.md)| - 想定通り動作していない場合にアクションを実行する|

## <a name="prerequisites"></a>前提条件

必要なライセンス [とアクセス許可に加](information-barriers.md#required-licenses-and-permissions)えて、次の要件を満たしていることを確認します。

- ディレクトリ データ - 組織の構造がディレクトリ データに反映されます。 このアクションを実行するには、グループ メンバーシップ、部署名などのユーザー アカウント属性が Azure Active Directory (または組織名) に正しくExchange Online。 詳細については、次のリソースを参照してください。
  - [情報障壁ポリシーの属性](information-barriers-attributes.md)
  - [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell でユーザー アカウント プロパティを構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- スコープディレクトリ検索 - 組織の最初の情報バリア ポリシーを定義する前に、スコープディレクトリ検索を有効にする[必要Microsoft Teams。](/MicrosoftTeams/teams-scoped-directory-search) 情報バリア ポリシーを設定または定義する前に、スコープディレクトリ検索を有効にしてから少なくとも 24 時間待ちます。

- EXO ライセンス - IB ポリシーは、ターゲット ユーザーに EXO ライセンスが割り当てられている場合にのみ機能します。

- 監査ログ - ポリシー アプリケーションの状態を確認するには、監査ログを有効にする必要があります。 セグメントまたはポリシーの定義を開始する前に、監査を有効にすることをお勧めします。 詳細については、「監査ログ検索 [を有効またはオフにする」を参照してください](turn-audit-log-search-on-or-off.md)。

- アドレス帳ポリシーなし - 情報バリア ポリシーを定義して適用する前に、Exchangeポリシーが適用されないか確認してください。 情報バリアはアドレス帳ポリシーに基づいていますが、2 種類のポリシーには互換性がありません。 このようなポリシーがある場合は、まずアドレス帳 [ポリシーを削除してください](/exchange/address-books/address-book-policies/remove-an-address-book-policy) 。 情報バリア ポリシーを有効にし、階層型アドレス帳を有効にすると、情報バリア セグメントに含まれていないすべてのユーザーに、Exchange[](/exchange/address-books/hierarchical-address-books/hierarchical-address-books)オンラインで階層アドレス帳が表示されます。

- PowerShell - 現在、情報バリア ポリシーは、PowerShell コマンドレットを使用して Office 365 セキュリティ &で定義および管理されます。 この記事ではいくつかの例を示しますが、PowerShell のコマンドレットとパラメーターを理解する必要があります。 また、このモジュールAzure PowerShell必要があります。
  - [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)
  - [モジュールのインストールAzure PowerShellする](/powershell/azure/install-az-ps)

- Microsoft Teams の情報バリアに対する管理者の同意 - IB ポリシーが適用されている場合、グループ (つまり、グループに基づく Teams チャネル) から IB 以外のコンプライアンス ユーザーを削除できます。 この構成は、組織がポリシーと規制に準拠し続けるのに役立ちます。 次の手順を使用して、情報バリア ポリシーが期待した通り動作Microsoft Teams。

   1. 前提条件: [インストール] からAzure PowerShellを[インストールAzure PowerShell。](/powershell/azure/install-az-ps)

   1. 次の PowerShell コマンドレットを実行します。

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. メッセージが表示されたら、仕事用または学校用のアカウントを使用してサインインOffice 365。

   1. [要求された **アクセス許可] ダイアログ** ボックスで、情報を確認し、[同意する] を **選択します**。 アプリによって要求されるアクセス許可は、以下に示します。

      > [!div class="mx-imgBorder"]
      > ![Image](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

すべての前提条件が満たされた場合は、次のセクションに進みます。

> [!TIP]
> 計画の準備を支援するために、この記事にはシナリオの例が含まれています。 [「Contoso の部署、セグメント、ポリシー」を参照してください](#example-contosos-departments-segments-and-policies)。<p>さらに、ダウンロード可能なExcelブックを使用して、セグメントとポリシーの計画と定義 (および PowerShell コマンドレットの作成) に役立ちます。 [ブックを取得します](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。

## <a name="part-1-segment-users"></a>パート 1: ユーザーのセグメント化

このフェーズでは、必要な情報バリア ポリシーを決定し、定義するセグメントの一覧を作成してから、セグメントを定義します。

### <a name="determine-what-policies-are-needed"></a>必要なポリシーを決定する

法律および業界の規制を考慮すると、組織内で情報バリア ポリシーが必要なグループは誰ですか? リストを作成します。 他のグループとの通信を妨げる必要があるグループはありますか? 他の 1 つまたは 2 つのグループとの通信のみを許可する必要があるグループはありますか? 次の 2 つのグループの 1 つに属するポリシーについて考えてください。

- "ブロック" ポリシーは、あるグループが別のグループと通信を妨げる。
- "許可" ポリシーを使用すると、グループは特定の特定の他の特定のグループとのみ通信できます。

グループとポリシーの最初の一覧がある場合は、必要なセグメントの特定に進みます。

### <a name="identify-segments"></a>セグメントの識別

ポリシーの最初の一覧に加えて、組織のセグメントの一覧を作成します。 情報バリア ポリシーに含まれるユーザーは、セグメントに属している必要があります。 ユーザーが 1 つのセグメントにのみ含め、セグメントを慎重に計画します。 各セグメントに適用できる情報バリア ポリシーは 1 つのみです。

> [!IMPORTANT]
> ユーザーは 1 つのセグメントにのみ含めできます。

セグメントの定義に使用する組織のディレクトリ データ内の属性を決定します。 *Department、MemberOf、* またはサポートされている属性を使用できます。  ユーザーに対して選択した属性に値が含まれます。 [情報バリアについては、サポートされている属性の一覧を参照してください](information-barriers-attributes.md)。

> [!IMPORTANT]
> **次のセクションに進む前に**、セグメントの定義に使用できる属性の値がディレクトリ データに含まれています。 ディレクトリ データに使用する属性の値が含されていない場合は、情報バリアを続行する前に、その情報を含めるユーザー アカウントを更新する必要があります。 このヘルプを表示するには、次のリソースを参照してください。<br/>- [PowerShell を使用してユーザー アカウントのOffice 365構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [ユーザープロファイルを使用してユーザーのプロファイル情報を追加または更新Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell を使用してセグメントを定義する

セグメントを定義しても、ユーザーには影響を及ぼします。情報バリア ポリシーを定義して適用するステージを設定するだけ。

1. 使用する属性に対応する **UserGroupFilter** パラメーターと一緒に **New-OrganizationSegment**[コマンドレットを](information-barriers-attributes.md)使用します。

    | 構文 | 例 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>この例では *、HR* というセグメントを、Department 属性の *値である HR* を使用して *定義* します。 コマンドレット **の -eq** 部分は"equals" を参照します。 (または、-ne を使用 **して"等** しくない" を意味できます。 セグメント [定義で "equals" と "not equals" を使用するを参照してください](#using-equals-and-not-equals-in-segment-definitions)。 |

    各コマンドレットを実行すると、新しいセグメントに関する詳細の一覧が表示されます。 詳細には、セグメントの種類、作成したユーザー、最後に変更したユーザーなどです。 

2. 定義するセグメントごとにこのプロセスを繰り返します。

    > [!IMPORTANT]
    > **セグメントが重ならないようにします**。 情報バリアの影響を受ける各ユーザーは、1 つのセグメント (および 1 つのみ) セグメントに属する必要があります。 ユーザーが 2 つ以上のセグメントに属している必要はありません。 (この記事 [の「例: Contoso の定義されたセグメント](#contosos-defined-segments) 」を参照してください)。

セグメントを定義した後、情報バリア [ポリシーの定義に進みます](#part-2-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>セグメント定義で "equals" と "not equals" を使用する

次の例では、"Department equals HR" のようなセグメントを定義しています。 

| 例 | 注 |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | この例では、セグメント定義に -eq と示される "equals" パラメーターが含 **まれています**。 |

次の表に示すように **、-ne** という "等しくない" パラメーターを使用してセグメントを定義することもできます。

| 構文 | 例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | この例では、Sales に含まれるすべてのユーザーを含む *NotSales* というセグメントを定義 *しました*。 コマンドレット **の -ne** 部分は"等しくない" を参照します。 |

"equals" または "not equals" を使用してセグメントを定義する以外に、"equals" パラメーターと "not equals" パラメーターの両方を使用してセグメントを定義できます。 論理 AND 演算子と OR 演算子を使用して、複雑なグループ フィルター *を**定義* することもできます。

| 構文 | 例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | この例では、ローカルに配置され、位置が一時としてリストされていないユーザーを含む *LocalFTE* というセグメントを定義 *しました*。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| この例では、セグメント *1* というセグメントを定義し、セグメントのメンバーではなく、group1@contoso.com のメンバーである group3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | この例では、セグメント *2* というセグメントを定義し、セグメントのメンバーではなく、group2@contoso.com メンバーであるユーザー group3@contoso.com。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| この例では *、Segment1and2* というセグメントを定義し、セグメントのメンバーではなく、group1@contoso.com および group2@contoso.com のメンバーを group3@contoso.com。 |

> [!TIP]
> 可能であれば、"-eq" または "-ne" を含むセグメント定義を使用します。 複雑なセグメント定義を定義しない。

## <a name="part-2-define-information-barrier-policies"></a>パート 2: 情報バリア ポリシーの定義

特定のセグメント間の通信を防止するか、通信を特定のセグメントに制限する必要があるかどうかを決定します。 理想的には、最小数のポリシーを使用して、組織が法的および業界の要件に準拠していることを確認します。

ユーザー セグメントの一覧と定義する情報バリア ポリシーを使用して、シナリオを選択し、手順に従います。

- [シナリオ 1: セグメント間の通信をブロックする](#scenario-1-block-communications-between-segments)
- [シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **ポリシーを定義する場合は、複数のポリシーをセグメントに割り当てないで下さい**。 たとえば、Sales というセグメントに 1 つのポリシーを定義する場合は、Sales に追加のポリシーを定義 *しない*。<p> さらに、情報バリア ポリシーを定義する場合は、ポリシーを適用する準備が整うまで、それらのポリシーを非アクティブな状態に設定してください。 ポリシーの定義 (または編集) は、これらのポリシーがアクティブな状態に設定され、適用されるまで、ユーザーには影響を与えかねない。

(この [記事の「例: Contoso](#contosos-information-barrier-policies) の情報バリア ポリシー」を参照してください)。

### <a name="scenario-1-block-communications-between-segments"></a>シナリオ 1: セグメント間の通信をブロックする

セグメント間の通信をブロックする場合は、方向ごとに 1 つという 2 つのポリシーを定義します。 各ポリシーは、一方向の通信のみをブロックします。

たとえば、セグメント A とセグメント B の間の通信をブロックするとします。この場合、セグメント A とセグメント B との通信を妨げる 1 つのポリシーを定義し、セグメント B がセグメント A と通信しなかねない 2 番目のポリシーを定義します。

1. 最初のブロック ポリシーを定義するには **、SegmentsBlocked パラメーターと一緒に New-InformationBarrierPolicy** **コマンドレットを使用** します。

    | 構文 | 例 |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、Sales というセグメントの *Sales-Research* というポリシーを定義 *しました*。 アクティブで適用されると、Sales のユーザーが *Research* というセグメントのユーザーとコミュニケーションを取るのを防 *ぐためです*。 |

2. 2 番目のブロック セグメントを定義するには、セグメントを逆にした **SegmentsBlocked** パラメーターで **New-InformationBarrierPolicy** コマンドレットを使用します。

    | 例 | 注 |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | この例では、Research-Sales というポリシーを定義 *して、Research* が *Sales* と通信しなか *からなかっています*。 |

3. 次のいずれかの操作に進みます。

   - (必要に応じて) [セグメントが他の 1 つのセグメントとのみ通信できるポリシーを定義する](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーの適用](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする

1. 1 つのセグメントが他の 1 つのセグメントと通信を許可するには **、SegmentsAllowed** パラメーターと一緒に **New-InformationBarrierPolicy** コマンドレットを使用します。

    | 構文 | 例 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> この例では、Manufacturing-HR というセグメントの *Manufacturing-HR* というポリシーを定義 *しました*。 アクティブで適用されている場合、このポリシーを使用すると、 *製造* のユーザーは HR というセグメントのユーザーとのみ通信 *できます*。 (この場合、 *製造は* 人事部門に含まれるユーザーと通信 *できません*。) |

    **必要に応じて、次の例に示すように、このコマンドレットで複数のセグメントを指定できます。**

    | 構文 | 例 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> この例では、リサーチ セグメントが HR と *製造* のみと通信できる *ポリシーを* 定義 *しました*。 |

    定義するポリシーごとにこの手順を繰り返して、特定のセグメントが特定の他の特定のセグメントとのみ通信することを許可します。

2. 次のいずれかの操作に進みます。

   - (必要に応じて) [セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments) 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーの適用](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>パート 3: 情報バリア ポリシーの適用

情報バリア ポリシーは、アクティブな状態に設定してからポリシーを適用するまで有効ではありません。

1. **Get-InformationBarrierPolicy** コマンドレットを使用して、定義されているポリシーの一覧を表示します。 各ポリシーの状態と ID (GUID) をメモします。

    構文: `Get-InformationBarrierPolicy`

2. ポリシーをアクティブな状態に設定するには、Identity パラメーターを指定して **Set-InformationBarrierPolicy** コマンドレットを使用し **、State** パラメーターを Active に設定 **します**。  

    | 構文 | 例 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* をアクティブな状態に設定します。 |

    ポリシーごとに必要に応じて、この手順を繰り返します。

3. 情報バリア ポリシーのアクティブな状態の設定が完了したら、セキュリティ & コンプライアンス センターの **Start-InformationBarrierPoliciesApplication** コマンドレットを使用します。

    構文: `Start-InformationBarrierPoliciesApplication`

    実行後、システムがポリシーの適用を開始するために `Start-InformationBarrierPoliciesApplication` 30 分かかります。 システムは、ユーザー別にポリシー ユーザーを適用します。 システムは、1 時間に約 5,000 のユーザー アカウントを処理します。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示する

PowerShell を使用すると、次の表に示すユーザー アカウント、セグメント、ポリシー、およびポリシー アプリケーションの状態を表示できます。

| この情報を表示するには | このアクションを実行する |
|:---------------|:----------|
| ユーザー アカウント | Identity パラメーター **を使用して Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 <p> 構文: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、標準ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p> 例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、次の 2 つのユーザー アカウントを参照Office 365 *meganb* for *Megan、Alex* の alexw *です。*  <p> (このコマンドレットは、1 人のユーザーにも使用できます `Get-InformationBarrierRecipientStatus -Identity <value>` 。 <p> このコマンドレットは、属性値や適用される情報バリア ポリシーなど、ユーザーに関する情報を返します。|
| セグメント | **Get-OrganizationSegment コマンドレットを使用** します。<p> 構文: `Get-OrganizationSegment` <p> このコマンドレットは、組織に定義されているすべてのセグメントの一覧を表示します。 |
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

## <a name="example-contosos-departments-segments-and-policies"></a>例: Contoso の部署、セグメント、およびポリシー

組織がセグメントおよびポリシーを定義する方法については、次の例を参照してください。

### <a name="contosos-departments-and-plan"></a>Contoso の部門とプラン

Contoso には、人事、営業、マーケティング、リサーチ、製造の5つの部門があります。 業界の規制に準拠し続けするために、一部の部署のユーザーは、次の表に示す他の部署と通信する必要があります。

| セグメント | に連絡できます | に連絡できません |
|:----------|:--------------|:-----------------|
| 人事 | すべてのユーザー | (制限なし) |
| 営業 | 人事、マーケティング、製造 | リサーチ |
| マーケティング | すべてのユーザー | (制限なし) |
| リサーチ | 人事、マーケティング、製造 | 営業 |
| 製造 | 人事、マーケティング | 人事またはマーケティング以外のユーザー |

この構造では、Contoso の計画には、次の 3 つの情報バリア ポリシーが含まれています。

1. Sales が Research と通信し(および Research と Sales との通信を妨げる別のポリシー) を防止するように設計されたポリシー。

2. 製造が人事およびマーケティングとのみ通信するように設計されたポリシー。

このシナリオでは、人事またはマーケティングのポリシーを定義する必要はありません。

### <a name="contosos-defined-segments"></a>Contoso の定義済みセグメント

Contoso は、次のように、Azure Active Directoryの Department 属性を使用してセグメントを定義します。

| 部門 | セグメント定義 |
|:-------------|:---------------------|
| 人事 | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| 営業 | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| マーケティング | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| リサーチ | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| 製造 | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

定義されたセグメントを使用して、Contoso がポリシーを定義します。

### <a name="contosos-information-barrier-policies"></a>Contoso の情報バリアポリシー

Contoso は、次の表で示すように 3 つのポリシーを定義します。

| ポリシー | ポリシー定義 |
|:---------|:--------------------|
| **ポリシー 1: 営業部門がリサーチ部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、情報バリアポリシーは、*営業-リサーチ* と呼ばれています。 このポリシーが適応されると、営業セグメント内のユーザーがリサーチセグメント内のユーザーと通信できなくなります。 このポリシーは一方通行ポリシーです。Research が Sales との通信を妨げない。 そのため、ポリシー2が必要です。 |
| **ポリシー 2: リサーチ部門が営業部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> この例では、情報バリアポリシーは、*リサーチ-営業* と呼ばれています。 このポリシーが適応されると、リサーチセグメント内のユーザーが、営業セグメント内のユーザーと通信できなくなります。 |
| **ポリシー 3: 製造と人事およびマーケティングの通信のみを許可する** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> この場合、情報バリアポリシーは、*製造-人事マーケティング* と呼ばれています。 このポリシーが適応されると、製造部門は人事およびマーケティング部門とだけ通信を行えます。 人事およびマーケティングは、他のセグメントとの通信を制限されません。 |

セグメントとポリシーが定義されている状態で、Contoso は **Start-InformationBarrierPoliciesApplication** コマンドレットを実行してポリシーを適用します。

コマンドレットが終了すると、Contoso は法的および業界の要件に準拠しています。

## <a name="resources"></a>リソース

- [情報バリアの概要を取得する](information-barriers.md)
- [詳細については、Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [オンラインでの情報バリアの詳細SharePointする](/sharepoint/information-barriers)
- [詳細については、「情報バリア」を参照OneDrive](/onedrive/information-barriers)
