---
title: 不正同意の付与を検出して修復する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MET150
description: 不正な同意許可攻撃を認識して修復する方法については、Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 263bffc6eb0fc45725fa91895b7197bf40d9a956
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202412"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>不正同意の付与を検出して修復する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**概要** 不正な同意許可攻撃を認識して修復する方法については、Microsoft 365。

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>不正な同意許可攻撃とは何Microsoft 365?

不正な同意許可攻撃では、攻撃者は連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録アプリケーションを作成します。 その後、攻撃者はエンド ユーザーに対して、フィッシング攻撃を通じて、または信頼できる Web サイトに不正なコードを挿入することで、アプリケーションが自分のデータにアクセスする同意を与える方法を悪用します。 不正なアプリケーションに同意が付与された後、組織のアカウントを必要とせずに、アカウント レベルでデータにアクセスできます。 侵害されたアカウントのパスワードのリセットやアカウントでの多要素認証 (MFA) の要求など、通常の修復手順は、サード パーティ製のアプリケーションであり、組織の外部であるため、この種類の攻撃に対して有効ではありません。

これらの攻撃は、情報を呼び出しているエンティティが人間ではなく自動化だと推測する対話モデルを利用します。

> [!IMPORTANT]
> アプリからの不正な同意許可に問題が発生している疑いはありますか。 Microsoft Cloud App Security (MCAS) には、OAuth アプリを検出、調査、修復するためのツールがあります。 この MCAS の記事には、リスクの高い [OAuth](/cloud-app-security/investigate-risky-oauth)アプリの調査について説明するチュートリアルがあります。 [また、OAuth](/cloud-app-security/app-permission-policy)アプリ ポリシーを設定して、これらのアプリを承認しているアプリ要求のアクセス許可を調査し、これらのアクセス許可要求を広く承認または禁止することもできます。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>不正な同意許可攻撃は、このサイトでどのようなMicrosoft 365?

監査ログを **検索して、** この攻撃の侵害のインジケーター (IOC) とも呼ばれる兆候を見つける必要があります。 多くの Azure 登録アプリケーションと大規模なユーザー ベースを持つ組織の場合、ベスト プラクティスは、組織の同意許可を毎週確認する方法です。

### <a name="steps-for-finding-signs-of-this-attack"></a>この攻撃の兆候を見つける手順

1. [ポータル] **Microsoft 365 Defender開き** <https://security.microsoft.com> 、[監査] を **選択します**。 または、[**監査**] ページに直接移動するには、<https://security.microsoft.com/auditlogsearch> を使用します。

2. [監査 **] ページ** で、[検索] タブ **が** 選択されているのを確認し、次の設定を構成します。
   - **日付と時刻の範囲**
   - **[アクティビティ**]: [すべての **アクティビティの結果を表示する] が選択** されているのを確認します。

   完了したら、[**検索**] をクリックします。

3. [アクティビティ] **列を** クリックして結果を並べ替え、[アプリケーションへの **同意] を探します**。

4. 一覧からエントリを選択して、アクティビティの詳細を表示します。 IsAdminContent が True に設定されている場合を確認します。

> [!NOTE]
>
> イベントが発生した後、対応する監査ログ エントリが検索結果に表示されるには、最大 30 分から 24 時間かかる場合があります。
>
> 監査レコードが保持され、監査ログで検索できる時間の長さは、Microsoft 365 サブスクリプション、特に特定のユーザーに割り当てられているライセンスの種類によって異なります。 詳細については、「監査ログ」 [を参照してください](../../compliance/search-the-audit-log-in-security-and-compliance.md)。
>
> この値が true の場合、グローバル管理者アクセス権を持つユーザーがデータへの広範なアクセスを許可した可能性があります。 予期しない場合は、攻撃を確認 [する手順を実行します](#how-to-confirm-an-attack)。

## <a name="how-to-confirm-an-attack"></a>攻撃を確認する方法

上記の IOC のインスタンスが 1 つ以上ある場合は、攻撃が発生したことを肯定的に確認するために、さらに調査を行う必要があります。 攻撃を確認するには、次の 3 つの方法を使用できます。

- ポータルを使用してアプリケーションとそのアクセス許可をインベントリAzure Active Directoryします。 この方法は十分ですが、一度に確認できるユーザーは 1 人のみです。多くのユーザーが確認できる場合は、非常に時間がかかる場合があります。
- PowerShell を使用してアプリケーションとそのアクセス許可をインベントリします。 これは最も速く、最も徹底的な方法であり、オーバーヘッドは最小です。
- ユーザーにアプリとアクセス許可を個別に確認し、結果を管理者に報告して修復を行います。

## <a name="inventory-apps-with-access-in-your-organization"></a>組織内のアクセス権を持つインベントリ アプリ

この操作は、Azure Active Directory ポータルまたは PowerShell を使用してユーザーに対して実行するか、ユーザーにアプリケーション アクセスを個別に列挙することができます。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>ポータルを使用Azure Active Directory手順

[ポータル] を使用して、個々のユーザーがアクセス許可を付与したアプリケーションをAzure Active Directoryできます <https://portal.azure.com> 。

1. 管理者権限を持つ Azure portal にサインインします。
2. [選択] ブレードAzure Active Directory選択します。
3. [**ユーザー**] を選択します。
4. 確認するユーザーを選択します。
5. [アプリケーション **] を選択します**。

これにより、ユーザーに割り当てられているアプリと、アプリケーションに与えるアクセス許可が表示されます。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>ユーザーがアプリケーション アクセスを列挙する手順

ユーザーにアクセスして、 <https://myapps.microsoft.com> 自分のアプリケーション アクセスを確認します。 アクセス権を持つすべてのアプリを表示し、そのアプリに関する詳細 (アクセス範囲を含む) を表示し、疑わしいアプリや不正なアプリに対する特権を取り消す必要があります。

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell でこれを行う手順

Illicit Consent Grant 攻撃を確認する最も簡単な方法は [ 、Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これは、テナント内のすべてのユーザーに対してすべての OAuth 同意許可と OAuth アプリを 1 つの .csv ファイルにダンプします。

#### <a name="pre-requisites"></a>前提条件

- Azure AD PowerShell ライブラリがインストールされています。
- スクリプトが実行されるテナントのグローバル管理者権限。
- スクリプトを実行するコンピューターのローカル管理者。

> [!IMPORTANT]
> 管理 ***アカウントで*** 多要素認証を必要とすることを強くお勧めします。 このスクリプトは MFA 認証をサポートします。

1. ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。

2. スクリプトを実行する[フォルダー](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)Get-AzureADPSPermissions.ps1からGitHubスクリプトをダウンロードまたはコピーします。 これは、出力 "permissions.csv" ファイルが書き込まれるのと同じフォルダーです。

3. PowerShell セッションを管理者として開き、スクリプトを保存したフォルダーを開きます。

4. Connect-AzureAD コマンドレットを使用してConnect[ディレクトリに移動](/powershell/module/azuread/connect-azuread)します。

5. 次の PowerShell コマンドを実行します。

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

スクリプトは、1 つのファイルを Permissions.csv。 次の手順に従って、不正なアプリケーションのアクセス許可の付与を探します。

1. ConsentType 列 (列 G) で値 "AllPrinciples" を検索します。 AllPrincipals アクセス許可を使用すると、クライアント アプリケーションはテナンシー内のすべてのユーザーのコンテンツにアクセスできます。 ネイティブ Microsoft 365アプリケーションは、このアクセス許可を正しく動作する必要があります。 このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重に確認する必要があります。

2. [アクセス許可] 列 (列 F) で、委任された各アプリケーションがコンテンツに対して持つアクセス許可を確認します。 "読み取り" および "書き込み" アクセス許可または "*" を探します。[すべて] アクセス許可を使用し、適切ではない可能性があるから、これらを慎重に確認します。

3. 同意が付与されている特定のユーザーを確認します。 高プロファイルまたは影響の大きなユーザーに不適切な同意が付与されている場合は、さらに調査する必要があります。

4. [ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。 スペルミスの名前、スーパーブランド名、またはハッカーサウンドの名前を持つアプリは、慎重に検討する必要があります。

## <a name="determine-the-scope-of-the-attack"></a>攻撃の範囲を特定する

アプリケーション アクセスのインベントリが完了したら、監査ログを **確認して** 侵害の全範囲を特定します。 影響を受けるユーザー、不正なアプリケーションが組織にアクセスしたタイム フレーム、およびアプリが持っていたアクセス許可を検索します。 監査ログは、**ポータルで**[検索Microsoft 365 Defenderできます](../../compliance/search-the-audit-log-in-security-and-compliance.md)。

> [!IMPORTANT]
> [この情報を取得](../../compliance/enable-mailbox-auditing.md)するには、管理者とユーザーのメールボックス監査とアクティビティ監査が攻撃の前に有効になっている必要があります。 [](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>不正な同意許可攻撃を停止して修復する方法

不正なアクセス許可を持つアプリケーションを特定した後、そのアクセスを削除する方法がいくつかあります。

- 次の方法で、アプリケーションのアクセス許可を Azure Active Directory取り消します。
  1. [ユーザー] ブレードで、影響 **を受けるAzure Active Directory移動** します。
  2. [アプリケーション **] を選択します**。
  3. 不正なアプリケーションを選択します。
  4. ドリルダウン **で [削除** ] をクリックします。

- [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従って、PowerShell で OAuth 同意付与を取り消します。

- [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従って、PowerShell を使用してサービス アプリの役割の割り当てを取り消します。

- また、影響を受けるアカウントのサインインを完全に無効にすることもできます。この場合、そのアカウントのデータへのアプリ アクセスが無効になります。 もちろん、これはエンド ユーザーの生産性にとって理想的な方法ではありません。ただし、影響を迅速に制限するために作業している場合、実行可能な短期的な修復になる可能性があります。

- テナンシーのために統合アプリケーションをオフにできます。 これは、エンド ユーザーがテナント全体で同意を付与する機能を無効にする抜本的な手順です。 これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことが可能です。 これは、ユーザーがサードパーティ アプリケーションで生産性を向上する能力を著しく損なうので、強く推奨されません。 これを行うには、「統合アプリをオンまたはオフにする」 [の手順に従います](../../admin/misc/user-consent.md)。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。 [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。
- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。
- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目

- [[アプリケーション] リストの予期しない](/azure/active-directory/application-access-unexpected-application) アプリケーションは、データにアクセスできる予期しないアプリケーションが発生した後に、管理者が実行する必要があるさまざまなアクションを実行します。
- [アプリケーションとアプリケーションAzure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent)は、同意とアクセス許可の概要です。
- [アプリケーションの開発に関する問題は、](/azure/active-directory/active-directory-application-dev-development-content-map) さまざまな同意関連記事へのリンクを提供します。
- [Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects)のアプリケーション プリンシパル オブジェクトとサービス プリンシパル オブジェクトは、アプリケーション モデルの中核となる Application および Service プリンシパル オブジェクトの概要を示します。
- [アプリへのアクセスの管理](/azure/active-directory/active-directory-managing-access-to-apps) は、管理者がアプリへのユーザー アクセスを管理する必要がある機能の概要です。
