---
title: 不正な同意許可を検出して修復する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.date: 07/28/2022
ms.localizationpriority: medium
search.appverid:
- MET150
description: Microsoft 365 での不正な同意許可攻撃を認識し、修復する方法について説明します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 354e32ca01a17be69f0bb144a437fd3e825613ea
ms.sourcegitcommit: 1e53bf8208c30d7b60685896207cc1142bebf34a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67059713"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>不正な同意許可を検出して修復する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**概要**  Microsoft 365 での不正な同意許可攻撃を認識し、修復する方法について説明します。

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>Microsoft 365 での不正な同意付与攻撃とは何ですか?

不正な同意許可攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録アプリケーションを作成します。 その後、攻撃者は、フィッシング攻撃を通じて、または信頼できる Web サイトに不正なコードを挿入することによって、そのアプリケーションにデータへのアクセスに同意することをエンド ユーザーに許可させます。 不正なアプリケーションに同意が与えられた後、組織のアカウントを必要とせずに、データに対するアカウント レベルのアクセス権を持ちます。 侵害されたアカウントのパスワードのリセットやアカウントでの多要素認証 (MFA) の要求など、通常の修復手順は、サード パーティ製のアプリケーションであり、組織の外部にあるため、この種の攻撃には対して有効ではありません。

これらの攻撃は、情報を呼び出しているエンティティが自動化であり、人間であると推測する相互作用モデルを利用します。

> [!IMPORTANT]
> 現在、アプリからの不正な同意許可に関する問題が発生していると思われますか? Microsoft Defender for Cloud Appsには、OAuth アプリを検出、調査、修復するためのツールがあります。 この Defender for Cloud Apps の記事には、 [危険な OAuth アプリの調査](/cloud-app-security/investigate-risky-oauth)に関する手順を説明するチュートリアルがあります。 [OAuth アプリ ポリシー](/cloud-app-security/app-permission-policy)を設定して、アプリが要求したアクセス許可 (ユーザーがこれらのアプリを承認している) を調査し、これらのアクセス許可要求を広く承認または禁止することもできます。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>Microsoft 365 では、不正な同意許可攻撃はどのようなものですか?

この攻撃の侵害のインジケーター (IOC) とも呼ばれる兆候を見つけるには、 **監査ログ** を検索する必要があります。 多くの Azure 登録済みアプリケーションと大規模なユーザー ベースを持つ組織の場合、ベスト プラクティスは、組織の同意付与を毎週確認することです。

### <a name="steps-for-finding-signs-of-this-attack"></a>この攻撃の兆候を見つけるための手順

1. Microsoft 365 Defender ポータルを開き<https://security.microsoft.com>、[**監査**] を選択します。 または、**[監査]** ページに直接移動するには、<https://security.microsoft.com/auditlogsearch> を使用します。

2. [ **監査** ] ページで、[ **検索** ] タブが選択されていることを確認し、次の設定を構成します。
   - **日付と時刻の範囲**
   - **アクティビティ**: **[すべてのアクティビティの結果を表示する** ] が選択されていることを確認します。

   完了したら、**[検索]** をクリックします。

3. [ **アクティビティ** ] 列をクリックして結果を並べ替え、[ **アプリケーションへの同意] を** 探します。

4. 一覧からエントリを選択すると、アクティビティの詳細が表示されます。 IsAdminConsent が True に設定されているかどうかを確認します。

> [!NOTE]
>
> イベントが発生した後に、対応する監査ログ エントリが検索結果に表示されるまでには、30 分から 24 時間かかる場合があります。
>
> 監査レコードが保持され、監査ログで検索できる時間の長さは、Microsoft 365 サブスクリプション、特に特定のユーザーに割り当てられているライセンスの種類によって異なります。 詳細については、「 [監査ログ](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。
>
> この値が true の場合は、グローバル管理者アクセス権を持つユーザーがデータへの広範なアクセスを許可している可能性があることを示します。 これが予期しない場合は、攻撃を [確認](#how-to-confirm-an-attack)する手順を実行します。

## <a name="how-to-confirm-an-attack"></a>攻撃を確認する方法

上記の IOC のインスタンスが 1 つ以上ある場合は、攻撃が発生したことを肯定的に確認するために、さらに調査を行う必要があります。 次の 3 つの方法のいずれかを使用して、攻撃を確認できます。

- Azure Active Directory ポータルを使用して、アプリケーションとそのアクセス許可をインベントリします。 この方法は徹底的ですが、確認するユーザーが多い場合は、一度に 1 人のユーザーしか確認できません。これは非常に時間がかかる場合があります。
- PowerShell を使用してアプリケーションとそのアクセス許可をインベントリします。 これは最も高速で最も徹底的な方法であり、オーバーヘッドの量が最も少ない方法です。
- ユーザーにアプリとアクセス許可を個別に確認し、結果を管理者に報告して修復を行います。

## <a name="inventory-apps-with-access-in-your-organization"></a>組織内のアクセス権を持つアプリをインベントリする

これを行うには、Azure Active Directory Portal または PowerShell を使用するか、ユーザーにアプリケーション アクセスを個別に列挙させます。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory ポータルを使用するための手順

Azure Active Directory Portal <https://portal.azure.com>を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。

1. 管理者権限でAzure portalにサインインします。
2. Azure Active Directory ブレードを選択します。
3. [**ユーザー**] を選択します。
4. 確認するユーザーを選択します。
5. **[アプリケーション]** を選択します。

これにより、ユーザーに割り当てられているアプリと、アプリケーションが持つアクセス許可が表示されます。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>ユーザーにアプリケーション アクセスを列挙させる手順

ユーザーに自分のアプリケーション へのアクセスを <https://myapps.microsoft.com> 確認してもらいます。 アクセス権を持つすべてのアプリを表示し、それらに関する詳細 (アクセスの範囲を含む) を表示し、疑わしいアプリや不正なアプリに対する特権を取り消すことができる必要があります。

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell でこれを行うための手順

不正アクセス許可の攻撃を確認する最も簡単な方法は [ 、Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーのすべての OAuth 同意許可と OAuth アプリが 1 つの.csv ファイルにダンプされます。

#### <a name="pre-requisites"></a>前提条件

- Azure AD PowerShell ライブラリがインストールされています。
- スクリプトを実行するテナントに対する権限をグローバル管理者します。
- スクリプトを実行するコンピューター上のローカル管理者。

> [!IMPORTANT]
> 管理アカウントで多要素認証を必要とすることを ***非常に推奨*** します。 このスクリプトでは、MFA 認証がサポートされています。

1. ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。

2. [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) スクリプトを GitHub からスクリプトを実行するフォルダーにダウンロードまたはコピーします。 これは、出力 "permissions.csv" ファイルが書き込まれるのと同じフォルダーになります。

3. 管理者として PowerShell セッションを開き、スクリプトの保存先フォルダーを開きます。

4. [Connect-AzureAD](/powershell/module/azuread/connect-azuread) コマンドレットを使用してディレクトリに接続します。

5. 次の PowerShell コマンドを実行します。

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

このスクリプトは、Permissions.csv という名前の 1 つのファイルを生成します。 不正なアプリケーションアクセス許可付与を探すには、次の手順に従います。

1. ConsentType 列 (列 G) で、値 "AllPrinciples" を検索します。 AllPrincipals アクセス許可を使用すると、クライアント アプリケーションはテナント内のすべてのユーザーのコンテンツにアクセスできます。 ネイティブ Microsoft 365 アプリケーションでは、正しく動作するには、このアクセス許可が必要です。 このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重に確認する必要があります。

2. [アクセス許可] 列 (列 F) で、委任された各アプリケーションがコンテンツに対して持つアクセス許可を確認します。 "読み取り" アクセス許可と "書き込み" アクセス許可または "すべて" アクセス許可を探し、適切でない可能性があるため、これらを慎重に確認します。

3. 同意が付与されている特定のユーザーを確認します。 高プロファイルまたは影響の大きいユーザーに不適切な同意が付与されている場合は、さらに調査する必要があります。

4. ClientDisplayName 列 (列 C) で、疑わしいと思われるアプリを探します。 名前のスペルミス、スーパー ブランド名、ハッカーの名前を含むアプリは、慎重に確認する必要があります。

## <a name="determine-the-scope-of-the-attack"></a>攻撃の範囲を決定する

アプリケーション アクセスのインベントリが完了したら、 **監査ログ** を確認して、侵害の完全な範囲を決定します。 影響を受けるユーザー、不正なアプリケーションが組織にアクセスできる期間、アプリが持っていたアクセス許可を検索します。 **監査ログ** は [、Microsoft 365 Defender ポータル](../../compliance/search-the-audit-log-in-security-and-compliance.md)で検索できます。

> [!IMPORTANT]
> この情報を取得するには、攻撃前に管理者とユーザーの[メールボックス監査](../../compliance/enable-mailbox-auditing.md)[とアクティビティ監査](../../compliance/turn-audit-log-search-on-or-off.md)が有効になっている必要があります。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>不正な同意許可攻撃を停止して修復する方法

不正アクセス許可を持つアプリケーションを特定したら、そのアクセスを削除する方法はいくつかあります。

- 次の方法で、Azure Active Directory Portal でアプリケーションのアクセス許可を取り消すことができます。
  1. **[Azure Active Directory** ユーザー] ブレードで、影響を受けるユーザーに移動します。
  2. **[アプリケーション]** を選択します。
  3. 不正なアプリケーションを選択します。
  4. ドリルダウンで **[削除]** をクリックします。

- [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant) の手順に従って、PowerShell で OAuth 同意付与を取り消すことができます。

- [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment) の手順に従って、PowerShell でサービス アプリ ロールの割り当てを取り消すことができます。

- 影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウント内のデータへのアプリ アクセスが無効になります。 これはエンド ユーザーの生産性には適していませんが、影響を迅速に制限する作業を行っている場合は、実行可能な短期的な修復になる可能性があります。

- テナントの統合アプリケーションをオフにすることができます。 これは、エンド ユーザーがテナント全体で同意を付与する機能を無効にする抜本的な手順です。 これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぎます。 これは、ユーザーがサード パーティのアプリケーションで生産性を高める能力を大幅に損なうので、強くお勧めしません。 これを行うには、「 [統合アプリを有効または無効にする](../../admin/misc/user-consent.md)」の手順に従います。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。 [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日間に実行するタスク。 これらは即座に影響を与え、ユーザーへの影響が低くなります。
- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。
- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目

- [アプリケーションの一覧の予期しないアプリケーション](/azure/active-directory/application-access-unexpected-application) では、データにアクセスできる予期しないアプリケーションがあることに気付いた後に、管理者が実行する必要があるさまざまなアクションについて説明します。
- [アプリケーションと Azure Active Directory の統合](/azure/active-directory/active-directory-apps-permissions-consent) は、同意とアクセス許可の概要です。
- [アプリケーションの開発に関する問題](/azure/active-directory/active-directory-application-dev-development-content-map) は、さまざまな同意に関連する記事へのリンクを提供します。
- [Azure Active Directory (Azure AD) のアプリケーション オブジェクトとサービス プリンシパル オブジェクト](/azure/active-directory/develop/active-directory-application-objects) は、アプリケーション モデルの中核となるアプリケーション およびサービス プリンシパル オブジェクトの概要を提供します。
- [アプリへのアクセスの管理](/azure/active-directory/active-directory-managing-access-to-apps) は、管理者がアプリへのユーザー アクセスを管理するために必要な機能の概要です。
