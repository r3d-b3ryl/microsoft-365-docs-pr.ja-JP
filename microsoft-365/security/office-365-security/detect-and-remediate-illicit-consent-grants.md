---
title: 不法な同意の付与を検出して修復する
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。
ms.openlocfilehash: 49fbbc1ea687cb5c01b39045a7359ee131a6732a
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "43808969"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>不法な同意の付与を検出して修復する

**概要** Office 365 で不法な同意を付与する攻撃を認識し、修復する方法について説明します。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Office 365 における不正な同意の付与攻撃

違法同意付与攻撃では、攻撃者は、連絡先情報、電子メール、ドキュメントなどのデータへのアクセスを要求する Azure 登録済みアプリケーションを作成します。 その後、攻撃者はエンドユーザーに対して、フィッシング攻撃によるデータへのアクセスを許可するように指示するか、または信頼された web サイトに不法なコードを挿入します。 不正なアプリケーションに同意した後は、組織のアカウントを使用しなくても、データへのアカウントレベルのアクセス権が付与されます。 違反アカウントのパスワードをリセットしたり、アカウントに多要素認証 (MFA) を必要としたりするなど、通常の修復手順は、この種の攻撃に対しては有効ではありません。これらはサードパーティのアプリケーションであり、組織の外部にあるためです。 

これらの攻撃は、情報を呼び出しているエンティティが人間ではなく、オートメーションであることを前提とする相互作用モデルを利用します。

> [!IMPORTANT]
> 現時点では、アプリからの不法な同意を得られる問題が発生していると思われますか。 Microsoft Cloud App Security (MCAS) には、OAuth アプリを検出、調査、修復するためのツールがあります。 この MCAS の記事には、[危険な OAuth アプリを調査](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)する方法の概要を示すチュートリアルがあります。 また、 [OAuth アプリポリシー](https://docs.microsoft.com/cloud-app-security/app-permission-policy)を設定して、アプリが要求するアクセス許可を調査し、ユーザーがこれらのアプリを承認して、これらのアクセス許可要求を幅広く承認または禁止することもできます。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Office 365 のように、不法な同意を与える攻撃はどのようになりますか?

**監査ログ**を検索して、この攻撃の兆候の兆候 (IOC) と呼ばれることもあります。 Azure に登録されているアプリケーションの数が多く、ユーザーが大規模な組織では、組織の同意の付与を週単位で確認することをお勧めします。

### <a name="steps-for-finding-signs-of-this-attack"></a>この攻撃の兆候を見つけるための手順

1. テナント内の [**セキュリティ & コンプライアンスセンター** ] を開きます。

2. [**検索**] に移動して、[**監査ログの検索**] を選択します。

3. 検索 (すべてのアクティビティとすべてのユーザー)、必要に応じて開始日と終了日を入力し、[**検索**] をクリックします。 

4. [**結果のフィルター** ] をクリックし、[**アクティビティ**] フィールドに「アプリケーションへの同意」と入力します。

5. 結果をクリックして、アクティビティの詳細を表示します。 [**詳細情報**] をクリックして、アクティビティの詳細を取得します。 IsAdminContent が True に設定されているかどうかを確認します。

> [!NOTE]
> イベントが発生した後に、対応する監査ログエントリが検索結果に表示されるようにするには、30分から最大24時間かかることがあります。 <br/><br/> 監査レコードが保持され、監査ログで検索可能な期間は、Microsoft 365 サブスクリプションによって異なり、具体的には特定のユーザーに割り当てられているライセンスの種類によって異なります。 詳細については、「[監査ログ](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。
> 
> この値が true の場合は、グローバル管理者のアクセス権を持つユーザーがデータへの広範なアクセス権を持っている可能性があることを示します。 これが予期しない場合は、[攻撃を確認](#how-to-confirm-an-attack)するための手順を実行します。

## <a name="how-to-confirm-an-attack"></a>攻撃を確認する方法

上記の IOCs のインスタンスが1つ以上ある場合は、攻撃が発生したことを確認するためにさらに調査する必要があります。 次の3つの方法のいずれかを使用して、攻撃を確認できます。

- Azure Active Directory ポータルを使用した、アプリケーションとそのアクセス許可の一覧を示します。 この方法は徹底していますが、チェックするユーザーが多い場合は、一度に1人のユーザーをチェックするだけで十分な時間がかかる場合があります。

- PowerShell を使用した、アプリケーションとそのアクセス許可の一覧を示します。 これは、最も少ないオーバーヘッドを最小限にした最も高速かつ最も綿密な方法です。

- ユーザーが自分のアプリとアクセス許可を個別に確認して、修復のために管理者に結果を報告するようにします。

## <a name="inventory-apps-with-access-in-your-organization"></a>組織内でアクセスできるインベントリアプリ

これは、Azure Active Directory ポータルまたは PowerShell を使用しているユーザーに対して行うことができます。または、ユーザーがアプリケーションアクセスを個別に列挙する必要があります。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Azure Active Directory ポータルを使用するための手順

[Azure Active Directory ポータル](https://portal.azure.com/)を使用して、個々のユーザーがアクセス許可を付与したアプリケーションを検索できます。

1. 管理者権限を使用して Azure Portal にサインインします。

2. Azure Active Directory ブレードを選択します。

3. [**ユーザー**] を選択します。

4. 確認するユーザーを選択します。

5. [**アプリケーション**] を選択します。

これにより、ユーザーに割り当てられているアプリと、アプリケーションのアクセス許可が表示されます。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>ユーザーがアプリケーションアクセスを列挙する手順

ユーザーが自分のアプリケーションhttps://myapps.microsoft.comへのアクセスを確認してもらいます。 これらのユーザーは、アクセス可能なすべてのアプリを表示したり、それらに関する詳細を表示したり (アクセスの範囲を含む)、疑わしいまたは不法なアプリに対して権限を取り消すことができます。

### <a name="steps-for-doing-this-with-powershell"></a>PowerShell を使用してこれを行うための手順

不法同意付与攻撃を確認する最も簡単な方法は、 [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)を実行することです。これにより、テナント内のすべてのユーザーの oauth 承諾許可と oauth アプリがすべて、1つの .csv ファイルにダンプされます。

#### <a name="pre-requisites"></a>前提条件

- Azure AD PowerShell ライブラリがインストールされていること。

- スクリプトが実行されるテナントのグローバル管理者権限。

- スクリプトを実行するコンピューターのローカル管理者。

> [!IMPORTANT]
> 管理アカウントでは、多要素認証を必要とすることを***強くお勧め***します。 このスクリプトは、MFA 認証をサポートします。

1. スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。

2. [Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)スクリプトを GitHub から、スクリプトを実行するフォルダーにダウンロードまたはコピーします。 これは、出力 "permissions" ファイルが書き込まれるフォルダーと同じです。

3. 管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。

4. [AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)コマンドレットを使用して、ディレクトリに接続します。

5. 次の PowerShell コマンドを実行します。

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

スクリプトによって、Permissions という名前のファイルが1つ作成されます。 次の手順に従って、不法なアプリケーションアクセス許可の付与を検索します。

1. [Conな種類] 列 (列 G) で、値 "AllPrinciples" を検索します。 AllPrincipals アクセス許可によって、クライアントアプリケーションは、テナント内のすべてのユーザーのコンテンツにアクセスできます。 ネイティブの Microsoft 365 アプリケーションは、このアクセス許可を正しく動作させるために必要です。 このアクセス許可を持つ Microsoft 以外のすべてのアプリケーションは、慎重にレビューする必要があります。

2. [アクセス許可] 列 (列 F) に、各委任されたアプリケーションがコンテンツに対して持っているアクセス許可を確認します。 "読み取り" と "書き込み" アクセス許可または "* を探します。All "アクセス許可を使用して、適切ではない可能性があるため慎重に確認してください。

3. 同意が付与されている特定のユーザーを確認します。 プロファイルが大きい場合や、影響度の高いユーザーに不適切な同意が付与されている場合は、さらに詳しく調査する必要があります。

4. [ClientDisplayName] 列 (列 C) で、疑わしいと思われるアプリを探します。 名前のスペルが間違っているアプリ、super bland names、またはハッカーが発音した名前は、慎重に検討する必要があります。

## <a name="determine-the-scope-of-the-attack"></a>攻撃の範囲を決定する

アプリケーションアクセスのインベントリ処理が終了したら、**監査ログ**を確認して、違反の完全な範囲を特定します。 影響を受けるユーザー、不法アプリケーションが組織にアクセスした時間枠、およびアプリのアクセス許可を検索します。 **監査ログ**は、 [Microsoft 365 セキュリティ/コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)で検索できます。

> [!IMPORTANT]
> この情報を取得するには、攻撃の前に、[管理者とユーザーの](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)[メールボックスの監査](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)とアクティビティの監査を有効にする必要があります。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>方法不法な同意の付与攻撃を停止および修復する方法

不法なアクセス許可を使用してアプリケーションを識別した後、そのアクセスを削除する方法がいくつかあります。

- Azure Active Directory ポータルのアプリケーションのアクセス許可は、次の方法で取り消すことができます。

  - **Azure Active Directory ユーザー**ブレードの影響を受けるユーザーに移動します。

  - [**アプリケーション**] を選択します。

  - 違法アプリケーションを選択します。

  - ドリルダウンで [**削除**] をクリックします。

- PowerShell で OAuth 同意の付与を取り消すには、 [AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)の手順に従ってください。

- PowerShell を使用してサービスアプリの役割の割り当てを無効にするには、 [AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)の手順に従ってください。

- 影響を受けるアカウントのサインインを完全に無効にすることもできます。これにより、そのアカウントのデータに対するアプリのアクセスが無効になります。 これは、エンドユーザーの生産性を向上させるのには理想的ではありませんが、影響をすばやく抑えるために作業する場合は、実用的な短期的な修復になります。

- テナントのために統合アプリケーションをオフにすることができます。 これは、エンドユーザーがテナント全体に同意を付与する機能を無効にする重大な手順です。 これにより、ユーザーが悪意のあるアプリケーションへのアクセスを誤って許可するのを防ぐことができます。 これは、ユーザーがサードパーティ製のアプリケーションを使用して生産性を向上させることがひどくないため、強くお勧めしません。 これを行うには、[統合アプリをオンまたはオフ](https://docs.microsoft.com/office365/admin/misc/integrated-apps)にする手順に従ってください。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>セキュリティで保護された Microsoft 365 (cybersecurity pro など)

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力な一連のセキュリティ機能が付属しています。 Microsoft 365 セキュリティロードマップを使用して、[最初の30日間、90日間、](security-roadmap.md) microsoft の推奨ベストプラクティスを実装し、microsoft の365テナントをセキュリティで保護することをお勧めします。

- 最初の30日間に実行するタスク。 これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。

- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目:

- [[自分のアプリケーション] リスト内の予期しないアプリケーション](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)は、データにアクセスするための予期しないアプリケーションがあることを認識した後に、管理者がさまざまなアクションを実行できるようにします。

- [アプリケーションを Azure Active Directory と統合](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)することは、同意とアクセス許可の概要です。

- [アプリケーションの開発に関する問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)さまざまな同意に関する記事へのリンクを提供します。

- 「 [Azure Active Directory のアプリケーションおよびサービスプリンシパルオブジェクト (AZURE AD)」で](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)は、アプリケーションモデルにとって中核となるアプリケーションおよびサービスプリンシパルオブジェクトの概要を示します。

- アプリへの[アクセスを管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)すると、管理者がアプリへのユーザーアクセスを管理するために必要な機能の概要が表示されます。
