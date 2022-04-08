---
title: 情報バリアの使用を開始する
description: 情報バリアの使用を開始する方法について説明します。
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
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb6de09c0c020631f42d8f2f09cb236affb94417
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713539"
---
# <a name="get-started-with-information-barriers"></a>情報バリアの使用を開始する

情報バリアを使用すると、ユーザーの特定のセグメントが相互に通信するのを防ぐか、特定のセグメントが特定の他のセグメントとのみ通信できるように設計されたポリシーを定義できます。 情報バリア ポリシーは、組織が関連する業界標準や規制への準拠を維持し、潜在的な競合を回避するのに役立ちます。 詳細については、「 [情報バリアの詳細」を](information-barriers.md)参照してください。

この記事では、情報バリア ポリシーを構成する方法について説明します。 いくつかの手順が関係するため、情報バリア ポリシーの構成を開始する前に、プロセス全体を確認してください。

> [!TIP]
> この記事には、情報バリア ポリシーの計画と定義に役立つ [シナリオの例](#example-scenario-contosos-departments-segments-and-policies) が含まれています。

## <a name="concepts"></a>概念

情報バリアのポリシーを定義する場合は、ユーザー アカウントの属性、セグメント、'ブロック' ポリシーまたは "許可" ポリシー、ポリシー アプリケーションを操作します。

- ユーザー アカウント属性は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、およびその他のジョブ プロファイルの詳細を含めることができます。
- セグメントは、選択したユーザー **アカウント属性** を使用してMicrosoft 365 コンプライアンス センターで定義されるユーザーのセットです。 ([サポートされる属性の一覧](information-barriers-attributes.md)を参照してください。)
- 情報バリア ポリシーは、通信の制限値または制限を決定します。 情報バリア ポリシーを定義する際は、次の 2 種類のポリシーから選択します。
  - *禁止* ポリシーは、あるセグメントと別のセグメントとの通信を禁止します。
  - *許可* ポリシーは、あるセグメントが他の特定のセグメントとのみ通信することを許可します。
- ポリシーの適用は、すべての情報バリア ポリシーが定義された後に実行され、組織に適用する準備が整います。

## <a name="configuration-at-a-glance"></a>構成の概要

| **手順** | **内容** |
|:------|:----------------|
| **手順 1**: [前提条件が満たされていることを確認する](#step-1-make-sure-prerequisites-are-met) | - [必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)があることを確認する<br/>- ディレクトリにユーザーをセグメント化するためのデータが含まれていることを確認する<br/>- [Microsoft Teamsの名前で検索を](/microsoftteams/teams-scoped-directory-search)有効にする<br/>- 監査ログの記録をオンにしてあることを確認する<br/>- Exchange アドレス帳ポリシーが設定されていないことを確認する<br/>- PowerShell を使用する (例が提供されています)<br/>- Microsoft Teamsの管理者の同意を提供する (手順が含まれています) |
| **手順 2**: [組織内のユーザーをセグメント化する](#step-2-segment-users-in-your-organization) | - 必要なポリシーを決定する<br/>- 定義するセグメントのリストを作成する<br/>- 使用する属性を特定する<br/>- ポリシー フィルターの観点からセグメントを定義する |
| **手順 3**: [情報バリア ポリシーを定義する](#step-3-define-information-barrier-policies) | - ポリシーを定義する (まだ適用しない)<br/>- 2 つの種類から選択します (ブロックまたは許可) |
| **手順 4**: [情報バリア ポリシーを適用する](#step-4-apply-information-barrier-policies) | - ポリシーをアクティブな状態に設定する<br/>- ポリシー アプリケーションを実行する<br/>- ポリシーの状態を表示する |
| **手順 5**: [SharePointとOneDriveに関する情報バリアの構成 (省略可能)](#step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive) | - SharePointとOneDriveの情報バリアを構成する |
| **手順 6**: [情報バリア モード (省略可能)](#step-6-information-barriers-modes) | - 情報バリア モードを更新する (該当する場合) |

## <a name="step-1-make-sure-prerequisites-are-met"></a>手順 1: 前提条件が満たされていることを確認する

[必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)に加えて、情報バリアを構成する前に、次の要件が満たされていることを確認してください。

- **ディレクトリ データ**: 組織の構造がディレクトリ データに反映されていることを確認してください。 この操作を実行するには、グループ メンバーシップ、部門名などのユーザー アカウント属性がAzure Active Directory (またはExchange Online) に正しく設定されていることを確認します。 詳細については、次のリソースを参照してください。
  - [情報障壁ポリシーの属性](information-barriers-attributes.md)
  - [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell でユーザー アカウント プロパティを構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- **スコープディレクトリ検索**: 組織の最初の情報バリア ポリシーを定義する前に、[Microsoft Teamsでスコープディレクトリ検索を有効にする](/MicrosoftTeams/teams-scoped-directory-search)必要があります。 情報バリア ポリシーを設定または定義する前に、スコープ付きディレクトリ検索を有効にしてから少なくとも 24 時間待ちます。

- **Exchange Online ライセンス**: 情報バリア ポリシーは、ターゲット ユーザーにExchange Online ライセンスが割り当てられている場合にのみ機能します。

- **監査ログが有効になっていることを確認** する: ポリシー アプリケーションの状態を検索するには、監査ログを有効にする必要があります。 Microsoft 365 の組織では、監査が既定で有効になっています。 組織によっては、特定の理由で監査を無効にしている場合があります。 組織の監査が無効になっている場合は、別の管理者が無効にしている可能性があります。 この手順を完了する場合は、監査を再びオンにしても問題ないか確認することをお勧めします。 詳細については、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」をご覧ください。

- **アドレス帳ポリシーなし**: 情報バリア ポリシーを定義して適用する前に、Exchangeアドレス帳ポリシーが設定されていないことを確認します。 情報バリアはアドレス帳ポリシーに基づいていますが、2 種類のポリシーには互換性がありません。 このようなポリシーがある場合は、最初に [アドレス帳ポリシーを削除](/exchange/address-books/address-book-policies/remove-an-address-book-policy) してください。 情報バリア ポリシーが有効になり、階層型アドレス帳が有効になると、情報バリア セグメントに **_含まれていない_** すべてのユーザーに、[階層型アドレス帳](/exchange/address-books/hierarchical-address-books/hierarchical-address-books)がオンラインでExchange表示されます。

- **PowerShell を使用して管理** する: 現在、セキュリティ & コンプライアンス センター PowerShell で情報バリア ポリシーが定義され、管理されています。 この記事ではいくつかの例を示していますが、PowerShell コマンドレットとパラメーターについて理解しておく必要があります。 Azure Active Directory PowerShell モジュールも必要になります。
  - [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)
  - [Graph用の PowerShell Azure Active Directoryインストールする](/powershell/azure/active-directory/install-adv2)

- **Microsoft Teamsの情報バリアに対する管理者の同意**: IB ポリシーが適用されると、IB 以外のコンプライアンス ユーザーをグループ (つまり、グループに基づくTeams チャネル) から削除できます。 この構成は、組織がポリシーと規制に準拠し続けるのに役立ちます。 次の手順を使用して、情報バリア ポリシーをMicrosoft Teamsで想定どおりに機能させます。

   1. 前提条件: [Graph用の PowerShell Azure Active Directoryインストール](/powershell/azure/active-directory/install-adv2)します。

   1. Windows PowerShell コマンドレットを実行します。

      ```powershell
      Connect-AzureAD -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzureAD -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -AppId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. メッセージが表示されたら、Office 365 の職場または学校用のアカウントを使用してサインインします。

   1. [ **要求されたアクセス許可** ] ダイアログ ボックスで、情報を確認し、[ **承諾**] を選択します。 アプリによって要求されるアクセス許可は次のとおりです。

      > [!div class="mx-imgBorder"]
      > ![イメージ。](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)

すべての前提条件が満たされたら、次の手順に進みます。

> [!TIP]
> 計画の準備を支援するために、この記事にはシナリオの例が含まれています。 [Contoso の部門、セグメント、ポリシーを参照してください](#example-scenario-contosos-departments-segments-and-policies)。

## <a name="step-2-segment-users-in-your-organization"></a>手順 2: 組織内のユーザーをセグメント化する

この手順では、必要な情報バリア ポリシーを決定し、定義するセグメントの一覧を作成し、セグメントを定義します。

### <a name="determine-what-policies-are-needed"></a>必要なポリシーを決定する

法的および業界の規制を考慮すると、情報バリア ポリシーを必要とする組織内のグループは誰ですか? リストを作成します。 他のグループとの通信を妨げる必要があるグループはありますか? 他の 1 つまたは 2 つのグループとの通信のみを許可する必要があるグループはありますか? 必要なポリシーは、次の 2 つのグループのいずれかに属していると考えてください。

- "ブロック" ポリシーでは、あるグループが別のグループと通信できなくなります。
- "許可" ポリシーを使用すると、グループは特定の他の特定の特定のグループとのみ通信できます。

グループとポリシーの最初の一覧が表示されたら、必要なセグメントの特定に進みます。

### <a name="identify-segments"></a>セグメントを識別する

ポリシーの最初の一覧に加えて、組織のセグメントの一覧を作成します。 情報バリア ポリシーに含まれるユーザーは、セグメントに属している必要があります。 ユーザーが 1 つのセグメントにのみ含めることができるので、セグメントを慎重に計画します。 各セグメントに適用できる情報バリア ポリシーは 1 つだけです。

> [!IMPORTANT]
> ユーザーは 1 つのセグメントにのみ含めることができます。

セグメントの定義に使用する組織のディレクトリ データの属性を決定します。 *Department*、*MemberOf*、またはサポートされている任意の属性を使用できます。 ユーザーに対して選択した属性に値があることを確認します。 [情報バリアについては、サポートされている属性の一覧を参照してください](information-barriers-attributes.md)。

> [!IMPORTANT]
> **次のセクションに進む前に、セグメントの定義に使用できる属性の値がディレクトリ データにあることを確認します**。 ディレクトリ データに使用する属性の値がない場合は、情報バリアを続行する前に、その情報を含むようにユーザー アカウントを更新する必要があります。 これに関するヘルプを表示するには、次のリソースを参照してください。<br/>- [PowerShell を使用してユーザー アカウントのプロパティOffice 365構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Azure Active Directoryを使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell を使用してセグメントを定義する

セグメントを定義しても、ユーザーには影響しません。情報バリア ポリシーを定義して適用するステージを設定するだけです。

1. 使用する [属性](information-barriers-attributes.md)に対応する **UserGroupFilter** パラメーターを使用して **、New-OrganizationSegment** コマンドレットを使用します。

    | 構文 | 例 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>この例では、*HR* と呼ばれるセグメントは、*部門* 属性の値である *HR* を使用して定義されます。 コマンドレットの **-eq** 部分は "equals" を参照します。 (または、 **-ne** を使用して "not equals" を意味することもできます。 [「セグメント定義で "equals" と "not equals" を使用する」を](#using-equals-and-not-equals-in-segment-definitions)参照してください)。 |

    各コマンドレットを実行すると、新しいセグメントに関する詳細の一覧が表示されます。 詳細には、セグメントの種類、作成したユーザーや最後に変更したユーザーなどが含まれます。 

2. 定義するセグメントごとに、このプロセスを繰り返します。

    > [!IMPORTANT]
    > **セグメントが重複していないことを確認します**。 情報バリアの影響を受ける各ユーザーは、1 つのセグメント (および 1 つだけ) に属している必要があります。 ユーザーが 2 つ以上のセグメントに属している必要はありません。 ( [例: この記事の Contoso の定義済みセグメントを](#contosos-defined-segments) 参照してください)。

セグメントを定義したら、 [情報バリア ポリシーの定義](#step-3-define-information-barrier-policies)に進みます。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>セグメント定義で "equals" と "not equals" を使用する

次の例では、"部門が人事に等しい" ようなセグメントを定義しています。 

| 例 | 注: |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | この例では、セグメント定義に **-eq** と示される "equals" パラメーターが含まれていることに注意してください。 |

次の表に示すように、 **-ne** と示される "not equals" パラメーターを使用してセグメントを定義することもできます。

| 構文 | 例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | この例では、*Sales* に参加していないすべてのユーザーを含む *NotSales* というセグメントを定義しました。 コマンドレットの **-ne** 部分は"等しくない" を参照します。 |

"equals" または "not equals" を使用してセグメントを定義するだけでなく、"equals" パラメーターと "not equals" パラメーターの両方を使用してセグメントを定義できます。 論理 *AND* 演算子と *OR* 演算子を使用して、複雑なグループ フィルターを定義することもできます。

| 構文 | 例 |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | この例では、 *LocalFTE* と呼ばれるセグメントを定義しました。これには、ローカルに配置され、その位置が *一時* として表示されないユーザーが含まれます。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| この例では、group3@contoso.com のメンバーではなく、group1@contoso.com のメンバーであるユーザーを含む *Segment1* というセグメントを定義しました。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | この例では、group3@contoso.com のメンバーではなく、group2@contoso.com のメンバーであるユーザーを含む *Segment2* というセグメントを定義しました。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| この例では、 *セグメント 1and2* というセグメントを定義しました。これには、group3@contoso.com のメンバーではなく、group1@contoso.com および group2@contoso.com のメンバーが含まれています。 |

> [!TIP]
> 可能であれば、"-eq" または "-ne" を含むセグメント定義を使用します。 複雑なセグメント定義を定義しないようにしてください。

## <a name="step-3-define-information-barrier-policies"></a>手順 3: 情報バリア ポリシーを定義する

特定のセグメント間の通信を防止するか、特定のセグメントに通信を制限する必要があるかどうかを決定します。 組織が法的および業界の要件に準拠していることを確認するために、ポリシーの最小数を使用するのが理想的です。

ユーザー セグメントの一覧と定義する情報バリア ポリシーを使用して、シナリオを選択し、手順に従います。

- [シナリオ 1: セグメント間の通信をブロックする](#scenario-1-block-communications-between-segments)
- [シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **ポリシーを定義するときに、セグメントに複数のポリシーを割り当てないように** してください。 たとえば、 *Sales* というセグメントに 1 つのポリシーを定義する場合は、 *Sales* に追加のポリシーを定義しないでください。<p> さらに、情報バリア ポリシーを定義するときに、ポリシーを適用する準備が整うまで、それらのポリシーを非アクティブ状態に設定してください。 ポリシーを定義 (または編集) しても、それらのポリシーがアクティブな状態に設定されてから適用されるまで、ユーザーには影響しません。

( [例: この記事の Contoso の情報バリア ポリシー](#contosos-information-barrier-policies) を参照してください)。

### <a name="scenario-1-block-communications-between-segments"></a>シナリオ 1: セグメント間の通信をブロックする

セグメント間の通信をブロックする場合は、方向ごとに 1 つずつ、2 つのポリシーを定義します。 各ポリシーは、一方向の通信のみをブロックします。

たとえば、セグメント A とセグメント B の間の通信をブロックするとします。この場合、セグメント A がセグメント B と通信できないようにする 1 つのポリシーを定義し、セグメント B がセグメント A と通信できないようにする 2 番目のポリシーを定義します。

1. 最初のブロック ポリシーを定義するには、**SegmentsBlocked** パラメーターを使用して **New-InformationBarrierPolicy** コマンドレットを使用します。

    | 構文 | 例 |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、Sales と *呼ばれる* セグメントに対して *Sales-Research* というポリシーを定義しました。 このポリシーをアクティブにして適用すると、 *Sales* のユーザーが *Research* というセグメントのユーザーと通信できなくなります。 |

2. 2 番目のブロック セグメントを定義するには、セグメントを逆にした状態で、 **新しい InformationBarrierPolicy** コマンドレットと **SegmentsBlocked** パラメーターを再度使用します。

    | 例 | 注: |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | この例では、Research-Sales と *通信できないようにする* *Research-Sales* というポリシーを定義 *しました*。 |

3. 次のいずれかの操作に進みます。

   - (必要な場合)[セグメントが他の 1 つのセグメントとのみ通信できるようにするポリシーを定義](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)する 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーを適用する](#step-4-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする

1. 1 つのセグメントが他の 1 つのセグメントと通信できるようにするには、**SegmentsAllowed** パラメーターを使用して **New-InformationBarrierPolicy** コマンドレットを使用します。

    | 構文 | 例 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> この例では、製造と呼ばれるセグメントに対して *Manufacturing-HR* というポリシーを定義 *しました*。 このポリシーをアクティブにして適用すると、 *製造* のユーザーは人事と呼ばれるセグメント内のユーザーとのみ通信 *できます*。 (この場合、 *製造* は *人事* 部に属していないユーザーと通信できません。 |

    **必要に応じて、次の例に示すように、このコマンドレットを使用して複数のセグメントを指定できます。**

    | 構文 | 例 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> この例では、 *リサーチ* セグメントが *人事* および製造者とのみ通信できるようにするポリシーを定義 *しました*。 |

    定義するポリシーごとにこの手順を繰り返して、特定のセグメントが他の特定のセグメントとのみ通信できるようにします。

2. 次のいずれかの操作に進みます。

   - (必要な場合) [セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments) 
   - (すべてのポリシーが定義された後) [情報バリア ポリシーを適用する](#step-4-apply-information-barrier-policies)

## <a name="step-4-apply-information-barrier-policies"></a>手順 4: 情報バリア ポリシーを適用する

情報バリア ポリシーは、アクティブ状態に設定してから、ポリシーを適用するまで有効になりません。

1. **Get-InformationBarrierPolicy** コマンドレットを使用して、定義されているポリシーの一覧を表示します。 各ポリシーの状態と ID (GUID) に注意してください。

    構文： `Get-InformationBarrierPolicy`

2. ポリシーをアクティブ状態に設定するには、**Id** パラメーターと **State** パラメーターを Active に設定して **Set-InformationBarrierPolicy** コマンドレットを使用 **します**。 

    | 構文 | 例 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* をアクティブな状態にする情報バリア ポリシーを設定します。 |

    各ポリシーに応じて、この手順を繰り返します。

3. 情報バリア ポリシーをアクティブな状態に設定し終えたら、セキュリティ & コンプライアンス センターの **Start-InformationBarrierPoliciesApplication** コマンドレットを使用します。

    構文： `Start-InformationBarrierPoliciesApplication`

    `Start-InformationBarrierPoliciesApplication` を実行した後、システムがポリシーを適用を開始するまで 30 分待ちます。 システムは、ユーザーごとにポリシーを適用します。 システムは、1 時間に約 5,000 のユーザー アカウントを処理します。

### <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示する

PowerShell を使用すると、次の表に示すように、ユーザー アカウント、セグメント、ポリシー、ポリシー アプリケーションの状態を表示できます。

| この情報を表示するには | このアクションを実行する |
|:---------------|:----------|
| ユーザー アカウント | Id パラメーターで **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 <p> 構文： `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p> 例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、Office 365の 2 つのユーザー アカウント (*meganb* for *Megan* と *alexw*) を参照します。 <p> (このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>` <p> このコマンドレットは、属性値や適用される情報バリア ポリシーなど、ユーザーに関する情報を返します。|
| セグメント | **Get-OrganizationSegment** コマンドレットを使用します。<p> 構文： `Get-OrganizationSegment` <p> このコマンドレットには、組織に定義されているすべてのセグメントの一覧が表示されます。 |
| 情報バリア ポリシー | **Get-InformationBarrierPolicy** コマンドレットを使用します。 <p> 構文： `Get-InformationBarrierPolicy` <p> このコマンドレットは、定義された情報バリア ポリシーとその状態の一覧を表示します。 |
| 最新の情報バリア ポリシー アプリケーション | **Get-InformationBarrierPoliciesApplicationStatus コマンドレットを** 使用します。 <p> 構文： `Get-InformationBarrierPoliciesApplicationStatus`<p> このコマンドレットは、ポリシー アプリケーションが完了したか、失敗したか、進行中であるかに関する情報を表示します。 |
| すべての情報バリア ポリシー アプリケーション|`Get-InformationBarrierPoliciesApplicationStatus -All` を使う<p> このコマンドレットは、ポリシー アプリケーションが完了したか、失敗したか、進行中であるかに関する情報を表示します。|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

### <a name="what-if-i-need-to-remove-or-change-policies"></a>ポリシーを削除または変更する必要がある場合はどうすればよいですか?

情報バリア ポリシーの管理に役立つリソースを利用できます。

- 情報バリアで問題が発生した場合は、「 [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)」を参照してください。
- ポリシーの適用を停止するには、「 [ポリシー アプリケーションの停止](information-barriers-edit-segments-policies.md#stop-a-policy-application)」を参照してください。
- 情報バリア ポリシーを削除するには、「ポリシー [の削除](information-barriers-edit-segments-policies.md#remove-a-policy)」を参照してください。
- セグメントまたはポリシーを変更するには、「情報バリア ポリシーの [編集 (または削除)」](information-barriers-edit-segments-policies.md)を参照してください。

## <a name="step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive"></a>手順 5: SharePointとOneDriveに関する情報バリアの構成

SharePointとOneDriveの情報バリアを構成する場合は、これらのサービスで情報バリアを有効にする必要があります。 また、Microsoft Teamsの情報バリアを構成する場合は、これらのサービスで情報バリアを有効にする必要もあります。 Microsoft Teams チームが作成されると、SharePoint サイトが自動的に作成され、ファイル エクスペリエンスのMicrosoft Teamsに関連付けられます。 情報バリア ポリシーは、既定では、この SharePoint サイトとファイルには適用されません。

SharePointとOneDriveで情報バリアを有効にするには、「SharePointで[情報バリアを使用](/sharepoint/information-barriers)する」のガイダンスと手順に従います。

## <a name="step-6-information-barriers-modes"></a>手順 6: 情報バリア モード

モードは、リソースの IB モードに基づいて、Microsoft 365 リソースへのアクセス、共有、メンバーシップを強化するのに役立ちます。 モードは、Microsoft 365 グループ、Microsoft Teams、OneDrive、SharePoint サイトでサポートされ、新しいまたは既存の IB 構成で自動的に有効になります。

Microsoft 365 リソースでは、次の IB モードがサポートされています。

| **Mode** | **Description** | **例** |
|:-----|:------------|:--------|
| **開く** | Microsoft 365 リソースに関連付けられている IB ポリシーやセグメントはありません。 だれでもリソースのメンバーとして招待できます。 | 組織用に作成されたチーム サイト。 |
| **所有者モデレート (プレビュー)** | Microsoft 365 リソースの IB ポリシーは、リソース所有者の IB ポリシーから決定されます。 リソース所有者は、IB ポリシーに基づいて任意のユーザーをリソースに招待できます。 このモードは、会社が所有者によってモデレートされている互換性のないセグメント ユーザー間のコラボレーションを許可する場合に便利です。 リソース所有者のみが、IB ポリシーに従って新しいメンバーを追加できます。 | 人事担当副社長は、営業およびリサーチの VM と共同作業したいと考えています。 IB モード *所有者モデレート* で設定された新しいSharePoint サイトで、Sales セグメントユーザーと Research セグメント ユーザーの両方を同じサイトに追加します。 リソースに適切なメンバーを確実に追加するのは、所有者の責任です。 |
| **暗黙的** | Microsoft 365 リソースの IB ポリシーまたはセグメントは、リソース メンバーの IB ポリシーから継承されます。 所有者は、リソースの既存のメンバーと互換性がある限り、メンバーを追加できます。 これは、Microsoft Teamsの既定の IB モードです。 | Sales セグメント ユーザーは、組織内の他の互換性のあるセグメントと共同作業するMicrosoft Teams チームを作成します。 |
| **Explicit** | Microsoft 365 リソースの IB ポリシーは、リソースに関連付けられているセグメントに従います。 リソース所有者またはSharePoint管理者は、リソースのセグメントを管理できます。  | Sales セグメントをサイトに関連付けて共同作業するために、Sales セグメント メンバー専用に作成されたサイト。   |

情報バリア モードとサービス間での構成方法の詳細については、次の記事を参照してください。

- [情報バリア モードと Microsoft Teams](/microsoftteams/information-barriers-in-teams)
- [情報バリア モードと OneDrive](/onedrive/information-barriers)
- [情報バリア モードと SharePoint](/sharepoint/information-barriers)

## <a name="example-scenario-contosos-departments-segments-and-policies"></a>シナリオの例: Contoso の部門、セグメント、ポリシー

組織がセグメントとポリシーを定義する方法を確認するには、次のシナリオ例を検討してください。

### <a name="contosos-departments-and-plan"></a>Contoso の部門とプラン

Contoso には、人事、営業、マーケティング、リサーチ、製造の5つの部門があります。 業界の規制に準拠し続けるために、次の表に示すように、一部の部門のユーザーは他の部門と通信することは想定されていません。

| セグメント | に連絡できます | に連絡できません |
|:----------|:--------------|:-----------------|
| 人事 | すべてのユーザー | (制限なし) |
| 営業 | 人事、マーケティング、製造 | 研究 |
| マーケティング | すべてのユーザー | (制限なし) |
| リサーチ | 人事、マーケティング、製造 | 営業 |
| 製造 | 人事、マーケティング | 人事またはマーケティング以外のユーザー |

この構造では、Contoso の計画には次の 3 つの情報バリア ポリシーが含まれています。

1. Sales がリサーチと通信できないようにするように設計されたポリシー (およびリサーチが Sales と通信できないようにする別のポリシー)。

2. 製造が人事およびマーケティングとのみ通信できるように設計されたポリシー。

このシナリオでは、人事またはマーケティングのポリシーを定義する必要はありません。

### <a name="contosos-defined-segments"></a>Contoso の定義済みセグメント

Contoso は、次のように、Azure Active Directoryの Department 属性を使用してセグメントを定義します。

| Department | セグメント定義 |
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
| **ポリシー 1: 営業部門がリサーチ部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、情報バリアポリシーは、*営業-リサーチ* と呼ばれています。 このポリシーが適応されると、営業セグメント内のユーザーがリサーチセグメント内のユーザーと通信できなくなります。 このポリシーは一方向のポリシーです。リサーチが Sales と通信することを妨げることはありません。 そのため、ポリシー2が必要です。 |
| **ポリシー 2: リサーチ部門が営業部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> この例では、情報バリアポリシーは、*リサーチ-営業* と呼ばれています。 このポリシーが適応されると、リサーチセグメント内のユーザーが、営業セグメント内のユーザーと通信できなくなります。 |
| **ポリシー 3: 製造が人事およびマーケティングとの通信のみを許可する** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> この場合、情報バリアポリシーは、*製造-人事マーケティング* と呼ばれています。 このポリシーが適応されると、製造部門は人事およびマーケティング部門とだけ通信を行えます。 人事およびマーケティングは、他のセグメントとの通信に制限されません。 |

セグメントとポリシーが定義されている場合、Contoso は **Start-InformationBarrierPoliciesApplication** コマンドレットを実行してポリシーを適用します。

コマンドレットが完了すると、Contoso は法的および業界の要件に準拠します。

## <a name="resources"></a>リソース

- [情報バリアの概要を確認する](information-barriers.md)
- [Microsoft Teamsの情報バリアの詳細を確認する](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDriveの情報バリアの詳細を確認する](/onedrive/information-barriers)
