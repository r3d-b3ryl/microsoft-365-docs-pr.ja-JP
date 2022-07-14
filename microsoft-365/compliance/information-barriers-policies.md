---
title: 情報バリアの使用を開始する
description: Microsoft Purview で情報バリアを使用する方法について説明します。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
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
ms.openlocfilehash: d2f2eb77dd143f82ced98f8fce424cc729e26df7
ms.sourcegitcommit: 221212fff9737e0ea386755deb8fed62ae9c254b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2022
ms.locfileid: "66787806"
---
# <a name="get-started-with-information-barriers"></a>情報バリアの使用を開始する

この記事では、組織で情報バリア (IB) ポリシーを構成する方法について説明します。 いくつかの手順が関係しているため、IB ポリシーの構成を開始する前に、プロセス全体を確認してください。

Microsoft Purview コンプライアンス ポータルを使用するか、[Office 365](https://compliance.microsoft.com)[セキュリティとコンプライアンスの PowerShell を](/powershell/exchange/scc-powershell)使用して、組織内で IB を構成します。 IB を初めて構成する組織の場合は、コンプライアンス ポータルで **情報バリア** ソリューションを使用することをお勧めします。 既存の IB 構成を管理していて、PowerShell を使い慣れている場合でも、このオプションを使用できます。

IB のシナリオと機能の詳細については、「 [情報バリアの詳細](information-barriers.md)」を参照してください。

> [!TIP]
> 計画の準備を支援するために、この記事には [シナリオの例](#example-scenario-contosos-departments-segments-and-policies) が含まれています。

## <a name="required-subscriptions-and-permissions"></a>必要なサブスクリプションとアクセス許可

IB の使用を開始する前に、Microsoft 365 サブスクリプションとアドオンを確認する必要があります。 IB にアクセスして使用するには、組織に次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5/A5 サブスクリプション (有料または試用版)
- Office 365 E5/A5/A3/A1 サブスクリプション (有料または試用版)
- Office 365 Advanced Compliance アドオン (新しいサブスクリプションでは使用できなくなります)
- Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 コンプライアンス アドオン
- Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 Insider Risk Management アドオン

詳細については、 [セキュリティ&コンプライアンスに関する Microsoft 365 ライセンス ガイダンスを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)参照してください。

[IB ポリシーを管理](information-barriers-policies.md)するには、次のいずれかのロールが割り当てられている必要があります。

- Microsoft 365 グローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理

役割とアクセス許可の詳細については、 [「Office 365 セキュリティ & コンプライアンス　センターのアクセス許可」](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)を参照してください。

## <a name="configuration-concepts"></a>構成の概念

IB を構成するときは、いくつかのオブジェクトと概念を操作します。

- **ユーザー アカウント属性** は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、およびその他のジョブ プロファイルの詳細を含めることができます。 これらの属性を持つセグメントにユーザーまたはグループを割り当てます。
- **セグメント** は、コンプライアンス ポータルで定義されているグループまたはユーザーのセットです。また、選択したグループまたはユーザー アカウントの属性を使用する PowerShell を使用します。 詳細については、 [IB でサポートされている属性](information-barriers-attributes.md) の一覧を参照してください。
- **IB ポリシーは、** 通信の制限または制限を決定します。 IB ポリシーを定義するときは、次の 2 種類のポリシーから選択します。
  - *禁止* ポリシーは、あるセグメントと別のセグメントとの通信を禁止します。
  - *許可* ポリシーは、あるセグメントが他の特定のセグメントとのみ通信することを許可します。

    > [!NOTE]
    > *許可* ポリシーの場合、IB 以外のグループとユーザーは、IB セグメントとポリシーに含まれるユーザーには表示されません。 IB 以外のグループとユーザーが IB セグメントとポリシーに含まれるユーザーに表示されるようにする必要がある場合は、 *ブロック* ポリシーを使用する必要があります。

- **ポリシー アプリケーション** は、すべての IB ポリシーが定義された後に実行され、組織で適用する準備が整いました。
- **IB 以外のユーザーとグループの可視性**。 IB 以外のユーザーとグループは、IB セグメントとポリシーから除外されたユーザーとグループです。 IB ポリシーの種類 (ブロックまたは許可) によって、これらのユーザーとグループの動作は、Microsoft Teams、SharePoint、OneDrive、およびグローバル アドレス一覧で異なります。 許可ポリシーで定義 *された* ユーザーの場合、IB 以外のグループとユーザーは、IB セグメントとポリシーに含まれるユーザーには表示されません。 *ブロック* ポリシーで定義されたユーザーの場合、IB 以外のグループとユーザーは、IB セグメントとポリシーに含まれるユーザーに表示されます。
- **グループのサポート**。 IB では現在、モダン グループのみがサポートされており、配布リスト/セキュリティ グループは IB 以外のグループとして扱われます。
- **非表示/無効のユーザー アカウント**。 組織内の非表示/無効なアカウントの場合、ユーザー アカウントが非表示または無効になっている場合、 *HiddenFromAddressListEnabled* パラメーターは自動的に *True* に設定されます。 IB 対応組織では、これらのアカウントが他のすべてのユーザー アカウントと通信できなくなります。 Microsoft Teams では、これらのアカウントを含むすべてのチャットがロックされるか、ユーザーが会話から自動的に削除されます。

## <a name="configuration-overview"></a>構成の概要

| **手順** | **内容** |
|:------|:----------------|
| **手順 1**: [前提条件が満たされていることを確認する](#step-1-make-sure-prerequisites-are-met) | - 必要なサブスクリプションとアクセス許可があることを確認する <br/>- ディレクトリにユーザーをセグメント化するためのデータが含まれていることを確認する<br/>- [Microsoft Teams の名前で検索を](/microsoftteams/teams-scoped-directory-search)有効にする<br/>- 監査ログの記録をオンにしてあることを確認する<br/>- Exchange アドレス帳ポリシーが設定されていないことを確認する <br/>- Microsoft Teams の管理者の同意を提供する (手順が含まれています) |
| **手順 2**: [組織内のユーザーをセグメント化する](#step-2-segment-users-in-your-organization) | - 必要なポリシーを決定する<br/>- 定義するセグメントのリストを作成する<br/>- 使用する属性を特定する<br/>- ポリシー フィルターの観点からセグメントを定義する |
| **手順 3**: [情報バリア ポリシーを作成する](#step-3-create-ib-policies) | - ポリシーを作成する (まだ適用しない)<br/>- 2 つの種類から選択します (ブロックまたは許可) |
| **手順 4**: [情報バリア ポリシーを適用する](#step-4-apply-ib-policies) | - ポリシーをアクティブな状態に設定する<br/>- ポリシー アプリケーションを実行する<br/>- ポリシーの状態を表示する |
| **手順 5**: [SharePoint と OneDrive の情報バリアの構成 (省略可能)](#step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive) | - SharePoint と OneDrive の IB を構成する |
| **手順 6**: [情報バリア モード (省略可能)](#step-6-information-barriers-modes) | - 該当する場合は IB モードを更新する |

## <a name="step-1-make-sure-prerequisites-are-met"></a>手順 1: 前提条件が満たされていることを確認する

必要なサブスクリプションとアクセス許可に加えて、IB を構成する前に、次の要件が満たされていることを確認してください。

- **ディレクトリ データ**: 組織の構造がディレクトリ データに反映されていることを確認してください。 この操作を実行するには、ユーザー アカウント属性 (グループ メンバーシップ、部署名など) が Azure Active Directory (またはExchange Online) に正しく設定されていることを確認します。 詳細については、次のリソースを参照してください。
  - [情報バリア ポリシーの属性](information-barriers-attributes.md)
  - [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell でユーザー アカウント プロパティを構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- **スコープ付きディレクトリ検索**: 組織の最初の IB ポリシーを定義する前に、 [Microsoft Teams でスコープ付きディレクトリ検索を有効にする](/MicrosoftTeams/teams-scoped-directory-search)必要があります。 IB ポリシーを設定または定義する前に、スコープ付きディレクトリ検索を有効にしてから少なくとも 24 時間待ちます。

- **監査ログが有効になっていることを確認** する: IB ポリシー アプリケーションの状態を検索するには、監査ログを有効にする必要があります。 Microsoft 365 の組織では、監査が既定で有効になっています。 組織によっては、特定の理由で監査を無効にしている場合があります。 組織の監査が無効になっている場合は、別の管理者が無効にしている可能性があります。 この手順を完了する場合は、監査を再びオンにしても問題ないか確認することをお勧めします。 詳細については、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」をご覧ください。

- **既存のExchange Onlineアドレス帳ポリシーを削除** する: IB ポリシーを定義して適用する前に、組織内のすべての既存のExchange Onlineアドレス帳ポリシーを削除する必要があります。 IB ポリシーはアドレス帳ポリシーに基づいており、既存の ABPs ポリシーは IB によって作成された ABP と互換性がありません。 既存のアドレス帳ポリシーを削除するには、「[Exchange Onlineでアドレス帳ポリシーを削除する](/exchange/address-books/address-book-policies/remove-an-address-book-policy)」を参照してください。 IB ポリシーとExchange Onlineの詳細については、「[情報バリアとExchange Online](information-barriers.md#information-barriers-and-exchange-online)」を参照してください。

- **PowerShell を使用して管理する (省略可能):** IB セグメントとポリシーは、Office 365 Security & Compliance PowerShell で定義および管理できます。 この記事ではいくつかの例を示していますが、PowerShell を使用して IB セグメントとポリシーを構成および管理する場合は、PowerShell コマンドレットとパラメーターについて理解しておく必要があります。 この構成オプションを選択した場合は、Azure Active Directory PowerShell モジュールも必要になります。
  - [セキュリティ/コンプライアンス PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)
  - [Azure Active Directory PowerShell for Graph のインストール](/powershell/azure/active-directory/install-adv2)

- **Microsoft Teams での IB の同意管理**: IB ポリシーが適用されると、IB 以外のコンプライアンス ユーザーをグループ (グループに基づく Teams チャネルなど) から削除できます。 この構成は、組織がポリシーと規制に準拠し続けるのに役立ちます。 次の手順に従って、MICROSOFT Teams で IB ポリシーを期待どおりに機能させます。

   1. 前提条件: [Azure Active Directory PowerShell for Graph をインストールします](/powershell/azure/active-directory/install-adv2)。

   2. Windows PowerShell コマンドレットを実行します。

      ```powershell
      Connect-AzureAD -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzureAD -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureADServicePrincipal -Filter "appid eq '$($appid)'"
      if ($sp -eq $null) { New-AzureADServicePrincipal -AppId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   3. メッセージが表示されたら、Office 365 の職場または学校用のアカウントを使用してサインインします。

   4. [ **要求されたアクセス許可** ] ダイアログ ボックスで、情報を確認し、[ **承諾**] を選択します。

すべての前提条件が満たされたら、次の手順に進みます。

## <a name="step-2-segment-users-in-your-organization"></a>手順 2: 組織内のユーザーをセグメント化する

この手順では、必要な IB ポリシーを決定し、セグメントを定義して定義するセグメントの一覧を作成します。 セグメントを定義してもユーザーには影響しません。IB ポリシーを定義して適用するステージを設定するだけです。

### <a name="determine-what-policies-are-needed"></a>必要なポリシーを決定する

組織のニーズを考慮して、IB ポリシーを必要とする組織内のグループを決定します。 次の点について理解しているかどうかを確認します。

- 組織内のグループとユーザー間のコミュニケーションとコラボレーションの制限を必要とする内部、法的、または業界の規制はありますか?
- 他のユーザー グループとの通信を妨げる必要があるグループやユーザーはありますか?
- 他の 1 つまたは 2 つのユーザー グループとの通信のみを許可する必要があるグループまたはユーザーはありますか?

必要なポリシーは、次の 2 種類のいずれかに属していると考えてください。

- *ブロック* ポリシーは、あるグループと別のグループの通信を禁止します。
- ポリシーを *許可すると*、グループは特定のグループとのみ通信できます。

必要なグループとポリシーの最初の一覧が表示されたら、IB ポリシーに必要なセグメントを特定します。

### <a name="identify-segments"></a>セグメントを識別する

ポリシーの最初の一覧に加えて、組織のセグメントの一覧を作成します。 IB ポリシーに含まれるユーザーは、セグメントに属している必要があります。 ユーザーが 1 つのセグメントにのみ含めることができるので、セグメントを慎重に計画します。 各セグメントに適用できる IB ポリシーは 1 つだけです。

> [!IMPORTANT]
> ユーザーは 1 つのセグメントにのみ含めることができます。

セグメントの定義に使用する組織のディレクトリ データの属性を決定します。 *Department*、*MemberOf*、またはサポートされている任意の IB 属性を使用できます。 ユーザーに対して選択した属性に値があることを確認します。 詳細については、 [IB でサポートされている属性を](information-barriers-attributes.md)参照してください。

> [!IMPORTANT]
> **次のセクションに進む前に、セグメントの定義に使用できる属性の値がディレクトリ データにあることを確認します**。 ディレクトリ データに使用する属性の値がない場合は、IB の構成を続行する前に、その情報を含むようにユーザー アカウントを更新する必要があります。 これに関するヘルプを表示するには、次のリソースを参照してください。<br/>- [PowerShell を使用してユーザー アカウントのプロパティOffice 365構成する](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-the-compliance-portal"></a>コンプライアンス ポータルを使用してセグメントを定義する

コンプライアンス ポータルでセグメントを定義するには、次の手順を実行します。

1. 組織内の管理者アカウントの資格情報を使用して [コンプライアンス ポータル](https://compliance.microsoft.com) にサインインします。
2. コンプライアンス ポータルで、[**情報バリア** >  セグメント] を選択 **します**。
3. [ **セグメント] ページで** 、[ **新しいセグメント** ] を選択して、新しいセグメントを作成して構成します。
4. [ **名前]** ページで、セグメントの名前を入力します。 セグメントが作成されたら、セグメントの名前を変更することはできません。
5. **[次へ]** を選択します。
6. [ **ユーザー グループ フィルター** ] ページで、[ **追加]** を選択して、セグメントのグループ属性とユーザー属性を構成します。 使用可能な属性の一覧からセグメントの属性を選択します。
7. 選択した属性に対して、[ *等しい* ] または *[等しくない* ] を選択し、属性の値を入力します。 たとえば、属性として *[部署]* と *[等号]* を選択した場合は、このセグメント条件に対して定義された部署として *「Marketing**」* と入力できます。 [条件の追加] を選択すると、属性の条件を **追加** できます。 属性または属性の条件を削除する必要がある場合は、属性または条件の削除アイコンを選択します。
8. **[ユーザー グループ フィルター**] ページで必要に応じて属性を追加し、[**次へ**] を選択します。
9. [ **設定の確認** ] ページで、セグメントに対して選択した設定と、選択した候補や警告を確認します。 [ **編集] を** 選択してセグメントの属性と条件を変更するか、[ **送信]** を選択してセグメントを作成します。

    > [!IMPORTANT]
    > **セグメントが重複していないことを確認します**。 IB ポリシーの影響を受ける各ユーザーは、1 つのセグメント (および 1 つだけ) に属している必要があります。 ユーザーが 2 つ以上のセグメントに属している必要はありません。 シナリオの例については、この記事の [Contoso の定義済みセグメントの例](#contosos-defined-segments) を参照してください。

### <a name="define-segments-using-powershell"></a>PowerShell を使用してセグメントを定義する

PowerShell でセグメントを定義するには、次の手順を実行します。

1. 使用する [属性](information-barriers-attributes.md)に対応する **UserGroupFilter** パラメーターを使用して **、New-OrganizationSegment** コマンドレットを使用します。

    | 構文 | 例 |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>この例では、*HR* と呼ばれるセグメントは、*部門* 属性の値である *HR* を使用して定義されます。 コマンドレットの **-eq** 部分は "equals" を参照します。 (または、 **-ne** を使用して "not equals" を意味することもできます。 [「セグメント定義で "equals" と "not equals" を使用する」を](#using-equals-and-not-equals-in-powershell-segment-definitions)参照してください)。 |

    各コマンドレットを実行すると、新しいセグメントに関する詳細の一覧が表示されます。 詳細には、セグメントの種類、作成したユーザーや最後に変更したユーザーなどが含まれます。 

2. 定義するセグメントごとに、このプロセスを繰り返します。

    > [!IMPORTANT]
    > **セグメントが重複していないことを確認します**。 IB ポリシーの影響を受ける各ユーザーは、1 つのセグメント (および 1 つだけ) に属している必要があります。 ユーザーが 2 つ以上のセグメントに属している必要はありません。 シナリオの例については、この記事の [Contoso の定義済みセグメントの例](#contosos-defined-segments) を参照してください。

セグメントを定義したら、 [手順 3: IB ポリシーの作成](#step-3-create-ib-policies)に進みます。

### <a name="using-equals-and-not-equals-in-powershell-segment-definitions"></a>PowerShell セグメント定義で "equals" と "not equals" を使用する

次の例では、PowerShell を使用して IB セグメントを構成し、"部門が HR に等しい" ようなセグメントを定義しています。

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
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | この例では、 *LocalFTE* と呼ばれるセグメントを定義しました。これには、ローカルに配置され、その位置が *一時* として表示されないユーザーが含まれています。 |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| この例では、group1@contoso.com のメンバーであり、group3@contoso.com のメンバーではないユーザーを含む *Segment1* というセグメントを定義しました。 |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | この例では、group2@contoso.com のメンバーであり、group3@contoso.com のメンバーではないユーザーを含む *Segment2* というセグメントを定義しました。 |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| この例では、group1@contoso.com と group2@contoso.com のユーザーを含み、group3@contoso.com のメンバーではなく、 *Segment1and2* というセグメントを定義しました。 |

> [!TIP]
> 可能であれば、"-eq" または "-ne" を含むセグメント定義を使用します。 複雑なセグメント定義を定義しないようにしてください。

## <a name="step-3-create-ib-policies"></a>手順 3: IB ポリシーを作成する

IB ポリシーを作成するときに、特定のセグメント間の通信を禁止するか、特定のセグメントへの通信を制限する必要があるかを判断します。 組織が内部、法的、業界の要件に準拠していることを確認するために、IB ポリシーの最小数を使用するのが理想的です。 コンプライアンス ポータルまたは PowerShell を使用して、IB ポリシーを作成して適用できます。

> [!TIP]
> ユーザー エクスペリエンスの一貫性を確保するために、可能であれば、ほとんどのシナリオでブロック ポリシーを使用することをお勧めします。

定義するユーザー セグメントと IB ポリシーの一覧を使用して、シナリオを選択し、手順に従います。

- [シナリオ 1: セグメント間の通信をブロックする](#scenario-1-block-communications-between-segments)
- [シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **ポリシーを定義するときに、セグメントに複数のポリシーを割り当てないように** してください。 たとえば、 *Sales* というセグメントに 1 つのポリシーを定義する場合は、 *Sales* セグメントに追加のポリシーを定義しないでください。<br> また、IB ポリシーを定義するときは、それらのポリシーを適用する準備が整うまで、それらのポリシーを非アクティブ状態に設定してください。 ポリシーを定義 (または編集) しても、それらのポリシーがアクティブな状態に設定されてから適用されるまで、ユーザーには影響しません。

### <a name="scenario-1-block-communications-between-segments"></a>シナリオ 1: セグメント間の通信をブロックする

セグメント間の通信をブロックする場合は、方向ごとに 1 つずつ、2 つのポリシーを定義します。 各ポリシーは、1 方向のみの通信をブロックします。

たとえば、セグメント A とセグメント B の間の通信をブロックするとします。この場合は、次の 2 つのポリシーを定義します。

- セグメント A がセグメント B と通信できないようにする 1 つのポリシー
- セグメント B がセグメント A と通信できないようにする 2 番目のポリシー

#### <a name="create-policies-using-the-compliance-portal-for-scenario-1"></a>シナリオ 1 のコンプライアンス ポータルを使用してポリシーを作成する

コンプライアンス ポータルでポリシーを定義するには、次の手順を実行します。

1. 組織内の管理者アカウントの資格情報を使用して [コンプライアンス ポータル](https://compliance.microsoft.com) にサインインします。
2. コンプライアンス ポータルで、[ **情報バリア** > **ポリシー**] を選択します。
3. [ **ポリシー** ] ページで、[ **ポリシーの作成** ] を選択し、新しい IB ポリシーを作成して構成します。
4. [ **名前]** ページで、ポリシーの名前を入力し、[ **次へ**] を選択します。
5. [ **割り当てられたセグメント** ] ページで、[セグメントの選択] を **選択します**。 検索ボックスを使用して、名前でセグメントを検索するか、スクロールして表示された一覧からセグメントを選択します。 [ **追加]** を選択して、選択したセグメントをポリシーに追加します。 セグメントは 1 つだけ選択できます。
6. **[次へ]** を選択します。
7. [ **通信とコラボレーション** ] ページで、[ **通信とコラボレーション** ] フィールドでポリシーの種類を選択します。 ポリシー オプションは *、[許可]* または *[ブロック] です*。 この例のシナリオでは、最初のポリシーに対して *[ブロック* ] が選択されます。

    >[!IMPORTANT]
    >セグメントの許可状態とブロック状態は、ポリシーの作成後に変更することはできません。 ポリシーの作成後に状態を変更するには、ポリシーを削除して新しいポリシーを作成する必要があります。

8. [ **セグメントの選択] を選択** して、ターゲット セグメントのアクションを定義します。 この手順では、複数のセグメントを割り当てることができます。 たとえば、*Sales* というセグメントのユーザーが *Research* というセグメントのユーザーと通信できないようにする場合は、手順 5 で *Sales* セグメントを定義し、この手順の [**セグメントの選択**] オプションで *Research* を割り当てます。
9. **[次へ]** を選択します。
10. [ **ポリシーの状態** ] ページで、アクティブなポリシーの状態を **[オン]** に切り替えます。 [**次へ**] を選んで続行します。
11. [ **設定の確認** ] ページで、ポリシーに対して選択した設定と、選択した候補や警告を確認します。 [ **編集] を** 選択していずれかのポリシー セグメントと状態を変更するか、[ **送信]** を選択してポリシーを作成します。

この例では、前の手順を繰り返して 2 つ目の *ブロック* ポリシーを作成し、 *Research* というセグメントのユーザーが *Sales* というセグメントのユーザーと通信できないように制限します。 手順 5 で *リサーチ* セグメントを定義し、[セグメントの **選択]** オプションで *Sales* (または複数のセグメント) を割り当てます。

#### <a name="create-policies-using-powershell-for-scenario-1"></a>シナリオ 1 の PowerShell を使用してポリシーを作成する

PowerShell でポリシーを定義するには、次の手順を実行します。

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
   - (すべてのポリシーが定義された後) [IB ポリシーを適用する](#step-4-apply-ib-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>シナリオ 2: セグメントが別のセグメント 1 つとだけ通信できるようにする

セグメントが他の 1 つのセグメントとの通信を許可する場合は、そのセグメントに対して 1 つのポリシーのみを定義します。 通信するセグメントには、同様の方向ポリシーは必要ありません (既定では、すべてのユーザーと通信して共同作業できるため)。

#### <a name="create-a-policy-using-the-compliance-portal-for-scenario-2"></a>シナリオ 2 のコンプライアンス ポータルを使用してポリシーを作成する

コンプライアンス ポータルでポリシーを定義するには、次の手順を実行します。

1. 組織内の管理者アカウントの資格情報を使用して [コンプライアンス ポータル](https://compliance.microsoft.com) にサインインします。
2. コンプライアンス ポータルで、[ **情報バリア** > **ポリシー**] を選択します。
3. [ **ポリシー** ] ページで、[ **ポリシーの作成** ] を選択し、新しい IB ポリシーを作成して構成します。
4. [ **名前]** ページで、ポリシーの名前を入力し、[ **次へ**] を選択します。
5. [ **割り当てられたセグメント** ] ページで、[セグメントの選択] を **選択します**。 検索ボックスを使用して、名前でセグメントを検索するか、スクロールして表示された一覧からセグメントを選択します。 [ **追加]** を選択して、選択したセグメントをポリシーに追加します。 セグメントは 1 つだけ選択できます。
6. **[次へ]** を選択します。
7. [ **通信とコラボレーション** ] ページで、[ **通信とコラボレーション** ] フィールドでポリシーの種類を選択します。 ポリシー オプションは *、[許可]* または *[ブロック] です*。 この例のシナリオでは、ポリシーに *[許可]* が選択されます。

    >[!IMPORTANT]
    >セグメントの許可状態とブロック状態は、ポリシーの作成後に変更することはできません。 ポリシーの作成後に状態を変更するには、ポリシーを削除して新しいポリシーを作成する必要があります。

8. [ **セグメントの選択] を選択** して、ターゲット セグメントのアクションを定義します。 この手順では、複数のセグメントを割り当てることができます。 たとえば、*製造* と呼ばれるセグメントのユーザーが *人事* というセグメントのユーザーと通信できるようにする場合は、手順 5 で *製造* セグメントを定義し、この手順の **[セグメントの選択**] オプションで *人事* を割り当てます。
9. **[次へ]** を選択します。
10. [ **ポリシーの状態** ] ページで、アクティブなポリシーの状態を **[オン]** に切り替えます。 [**次へ**] を選んで続行します。
11. [ **設定の確認** ] ページで、ポリシーに対して選択した設定と、選択した候補や警告を確認します。 [ **編集] を** 選択していずれかのポリシー セグメントと状態を変更するか、[ **送信]** を選択してポリシーを作成します。

#### <a name="create-a-policy-using-powershell-for-scenario-2"></a>シナリオ 2 の PowerShell を使用してポリシーを作成する

PowerShell でポリシーを定義するには、次の手順を実行します。

1. 1 つのセグメントが他の 1 つのセグメントと通信できるようにするには、**SegmentsAllowed** パラメーターを使用して **New-InformationBarrierPolicy** コマンドレットを使用します。

    | 構文 | 例 |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> この例では、製造と呼ばれるセグメントに対して *Manufacturing-HR* というポリシーを定義 *しました*。 このポリシーをアクティブにして適用すると、 *製造* のユーザーは人事と呼ばれるセグメント内のユーザーとのみ通信 *できます*。 この場合、 *製造* は *人事* 部に属していないユーザーと通信できません。 |

    **必要に応じて、次の例に示すように、このコマンドレットを使用して複数のセグメントを指定できます。**

    | 構文 | 例 |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> この例では、 *リサーチ* セグメントが *人事* および製造者とのみ通信できるようにするポリシーを定義 *しました*。 |

    定義するポリシーごとにこの手順を繰り返して、特定のセグメントが他の特定のセグメントとのみ通信できるようにします。

2. 次のいずれかの操作に進みます。

   - (必要な場合) [セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments) 
   - (すべてのポリシーが定義された後) [IB ポリシーを適用する](#step-4-apply-ib-policies)

## <a name="step-4-apply-ib-policies"></a>手順 4: IB ポリシーを適用する

IB ポリシーは、アクティブな状態に設定してポリシーを適用するまで有効になりません。

### <a name="apply-policies-using-the-compliance-portal"></a>コンプライアンス ポータルを使用してポリシーを適用する

コンプライアンス ポータルでポリシーを適用するには、次の手順を実行します。

1. 組織内の管理者アカウントの資格情報を使用して [コンプライアンス ポータル](https://compliance.microsoft.com) にサインインします。
2. コンプライアンス ポータルで、 **情報バリア** > **ポリシー アプリケーション** を選択します。
3. [ **ポリシー] アプリケーション** ページで、[ **すべてのポリシーを適用]** を選択して、組織内のすべての IB ポリシーを適用します。

    >[!NOTE]
    >システムがポリシーの適用を開始するには、30 分かかります。 システムは、ユーザーごとにポリシーを適用します。 システムは、1 時間に約 5,000 のユーザー アカウントを処理します。

### <a name="apply-policies-using-powershell"></a>PowerShell を使用してポリシーを適用する

PowerShell を使用してポリシーを適用するには、次の手順を実行します。

1. **Get-InformationBarrierPolicy** コマンドレットを使用して、定義されているポリシーの一覧を表示します。 各ポリシーの状態と ID (GUID) に注意してください。

    構文： `Get-InformationBarrierPolicy`

2. ポリシーをアクティブ状態に設定するには、**Id** パラメーターと **State** パラメーターを Active に設定して **Set-InformationBarrierPolicy** コマンドレットを使用 **します**。 

    | 構文 | 例 |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> この例では、GUID *43c37853-ea10-4b90-a23d-ab8c93772471* をアクティブな状態にする IB ポリシーを設定します。 |

    各ポリシーに応じて、この手順を繰り返します。

3. IB ポリシーをアクティブな状態に設定し終えたら、Security & Compliance PowerShell の **Start-InformationBarrierPoliciesApplication** コマンドレットを使用します。

    構文： `Start-InformationBarrierPoliciesApplication`

    `Start-InformationBarrierPoliciesApplication` を実行した後、システムがポリシーを適用を開始するまで 30 分待ちます。 システムは、ユーザーごとにポリシーを適用します。 システムは、1 時間に約 5,000 のユーザー アカウントを処理します。

### <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>ユーザー アカウント、セグメント、ポリシー、またはポリシー アプリケーションの状態を表示する

PowerShell を使用すると、次の表に示すように、ユーザー アカウント、セグメント、ポリシー、ポリシー アプリケーションの状態を表示できます。

| この情報を表示するには | このアクションを実行する |
|:---------------|:----------|
| ユーザー アカウント | Id パラメーターで **Get-InformationBarrierRecipientStatus** コマンドレットを使用します。 <p> 構文： `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> 名前、エイリアス、識別名、正規ドメイン名、電子メール アドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p> 例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> この例では、Office 365の 2 つのユーザー アカウント (*meganb* for *Megan* と *alexw*) を参照します。 <p> (このコマンドレットは、1 人のユーザーに対して使用することもできます。 `Get-InformationBarrierRecipientStatus -Identity <value>` <p> このコマンドレットは、属性値や適用されるすべての IB ポリシーなど、ユーザーに関する情報を返します。|
| セグメント | **Get-OrganizationSegment** コマンドレットを使用します。<p> 構文： `Get-OrganizationSegment` <p> このコマンドレットには、組織に定義されているすべてのセグメントの一覧が表示されます。 |
| IB ポリシー | **Get-InformationBarrierPolicy** コマンドレットを使用します。 <p> 構文： `Get-InformationBarrierPolicy` <p> このコマンドレットには、定義された IB ポリシーの一覧とその状態が表示されます。 |
| 最新の IB ポリシー アプリケーション | **Get-InformationBarrierPoliciesApplicationStatus コマンドレットを** 使用します。 <p> 構文： `Get-InformationBarrierPoliciesApplicationStatus`<p> このコマンドレットは、ポリシー アプリケーションが完了したか、失敗したか、進行中であるかに関する情報を表示します。 |
| すべての IB ポリシー アプリケーション|`Get-InformationBarrierPoliciesApplicationStatus -All` を使う<p> このコマンドレットは、ポリシー アプリケーションが完了したか、失敗したか、進行中であるかに関する情報を表示します。|

### <a name="what-if-i-need-to-remove-or-change-policies"></a>ポリシーを削除または変更する必要がある場合はどうすればよいですか?

IB ポリシーの管理に役立つリソースを利用できます。

- IB ポリシーを編集、停止、または削除するには、「 [情報バリア](information-barriers-edit-segments-policies.md) ポリシーの管理」を参照してください。
- IB で問題が発生した場合は、「 [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)」を参照してください。

## <a name="step-5-configuration-for-information-barriers-on-sharepoint-and-onedrive"></a>手順 5: SharePoint と OneDrive の情報バリアの構成

SharePoint と OneDrive の IB を構成する場合は、これらのサービスで IB を有効にする必要があります。 Microsoft Teams 用に IB を構成する場合は、これらのサービスで IB を有効にする必要もあります。 Microsoft Teams チームでチームを作成すると、SharePoint サイトが自動的に作成され、ファイル エクスペリエンスのために Microsoft Teams に関連付けられます。 IB ポリシーは、この新しい SharePoint サイトとファイルでは既定では適用されません。

SharePoint と OneDrive で IB を有効にするには、「SharePoint で [情報バリアを使用](/sharepoint/information-barriers) する」のガイダンスと手順に従います。

## <a name="step-6-information-barriers-modes"></a>手順 6: 情報バリア モード

モードは、リソースの IB モードに基づいて、Microsoft 365 リソースのアクセス、共有、メンバーシップを強化するのに役立ちます。 モードは、Microsoft 365 グループ、Microsoft Teams、OneDrive、SharePoint サイトでサポートされ、新規または既存の IB 構成で自動的に有効になります。

Microsoft 365 リソースでは、次の IB モードがサポートされています。

| **Mode** | **Description** | **例** |
|:-----|:------------|:--------|
| **開く** | Microsoft 365 リソースに関連付けられている IB ポリシーやセグメントはありません。 だれでもリソースのメンバーとして招待できます。 | 組織用に作成されたチーム サイト。 |
| **所有者モデレート (プレビュー)** | Microsoft 365 リソースの IB ポリシーは、リソース所有者の IB ポリシーから決定されます。 リソース所有者は、IB ポリシーに基づいて任意のユーザーをリソースに招待できます。 このモードは、会社が所有者によってモデレートされている互換性のないセグメント ユーザー間のコラボレーションを許可する場合に便利です。 リソース所有者のみが、IB ポリシーに従って新しいメンバーを追加できます。 | 人事担当副社長は、営業およびリサーチの VM と共同作業したいと考えています。 IB モード *所有者モデレート* で設定され、Sales セグメントと Research セグメントユーザーの両方を同じサイトに追加する新しい SharePoint サイト。 適切なメンバーがリソースに追加されるようにするのは、所有者の責任です。 |
| **暗黙的** | Microsoft 365 リソースの IB ポリシーまたはセグメントは、リソース メンバーの IB ポリシーから継承されます。 所有者は、リソースの既存のメンバーと互換性がある限り、メンバーを追加できます。 このモードは、Microsoft Teams の既定の IB モードです。 | Sales セグメント ユーザーは、組織内の他の互換性のあるセグメントと共同作業する Microsoft Teams チームを作成します。 |
| **Explicit** | Microsoft 365 リソースの IB ポリシーは、リソースに関連付けられているセグメントに従います。 リソース所有者または SharePoint 管理者は、リソースのセグメントを管理できます。 | Sales セグメントをサイトに関連付けて共同作業するために、Sales セグメント メンバー専用に作成されたサイト。 |
| **混合 (プレビュー)** | OneDrive にのみ適用されます。 OneDrive の IB ポリシーは、OneDrive に関連付けられているセグメントに従います。 リソース所有者または OneDrive 管理者には、リソースのセグメントを管理する機能があります。 | Sales セグメントメンバーが共同作業するために作成した OneDrive は、セグメント化されていないユーザーと共有できます。 |

IB モードとサービス間での構成方法の詳細については、次の記事を参照してください。

- [情報バリア モードと Microsoft Teams](/microsoftteams/information-barriers-in-teams)
- [情報バリア モードと OneDrive](/onedrive/information-barriers)
- [情報バリア モードと SharePoint](/sharepoint/information-barriers)

## <a name="example-scenario-contosos-departments-segments-and-policies"></a>シナリオの例: Contoso の部門、セグメント、ポリシー

組織がセグメントとポリシーを定義する方法を確認するには、次のシナリオ例を検討してください。

### <a name="contosos-departments-and-plan"></a>Contoso の部門とプラン

Contoso には、 *人事*、 *営業*、 *マーケティング*、 *リサーチ*、 *製造* の 5 つの部門があります。 業界の規制に準拠し続けるために、次の表に示すように、一部の部門のユーザーは他の部門と通信することは想定されていません。

| **セグメント** | **通信可能** | **通信できない** |
|:------------|:-------------------------|:---------------------------|
| HR | すべてのユーザー | (制限なし) |
| 営業 | 人事、マーケティング、製造 | 研究 |
| マーケティング | すべてのユーザー | (制限なし) |
| リサーチ | 人事、マーケティング、製造 | 営業 |
| 製造 | 人事、マーケティング | 人事またはマーケティング以外のユーザー |

この構造では、Contoso の計画には次の 3 つの IB ポリシーが含まれます。

1. Sales が Research と通信できないように設計された IB ポリシー
2. リサーチが Sales と通信できないようにするためのもう 1 つの IB ポリシー。
3. 製造が人事およびマーケティングとの通信のみを許可するように設計された IB ポリシー。

このシナリオでは、 *人事* または *マーケティング* の IB ポリシーを定義する必要はありません。

### <a name="contosos-defined-segments"></a>Contoso の定義済みセグメント

Contoso は、次のように、Azure Active Directory の Department 属性を使用してセグメントを定義します。

| 部署 | セグメント定義 |
|:-------------|:---------------------|
| 人事 | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| 営業 | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| マーケティング | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| リサーチ | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| 製造 | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

セグメントが定義された状態で、Contoso は IB ポリシーの定義に進みます。

### <a name="contosos-ib-policies"></a>Contoso の IB ポリシー

Contoso では、次の表に示すように、3 つの IB ポリシーを定義します。

| ポリシー | ポリシー定義 |
|:---------|:--------------------|
| **ポリシー 1: 営業部門がリサーチ部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、IB ポリシーは *Sales-Research* と呼ばれます。 このポリシーが適応されると、営業セグメント内のユーザーがリサーチセグメント内のユーザーと通信できなくなります。 このポリシーは一方向のポリシーです。リサーチが Sales と通信することを妨げることはありません。 そのため、ポリシー2が必要です。 |
| **ポリシー 2: リサーチ部門が営業部門と通信できないようにする** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> この例では、IB ポリシーは *Research-Sales* と呼ばれます。 このポリシーが適応されると、リサーチセグメント内のユーザーが、営業セグメント内のユーザーと通信できなくなります。 |
| **ポリシー 3: 製造が人事およびマーケティングとの通信のみを許可する** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> この場合、IB ポリシーは *Manufacturing-HRMarketing* と呼ばれます。 このポリシーが適応されると、製造部門は人事およびマーケティング部門とだけ通信を行えます。 人事とマーケティングは、他のセグメントとの通信を制限されません。 |

セグメントとポリシーが定義されている場合、Contoso は **Start-InformationBarrierPoliciesApplication** コマンドレットを実行してポリシーを適用します。

コマンドレットが完了すると、Contoso は業界の要件に準拠します。

## <a name="resources"></a>リソース

- [情報バリアについての詳細情報](information-barriers.md)
- [Microsoft Teams の情報バリアの詳細を確認する](/MicrosoftTeams/information-barriers-in-teams)
- [SharePoint Online の情報バリアの詳細](/sharepoint/information-barriers)
- [OneDrive の情報バリアの詳細を確認する](/onedrive/information-barriers)
