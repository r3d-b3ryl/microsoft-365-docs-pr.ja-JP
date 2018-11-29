---
title: 'フェーズ 2: ID インフラストラクチャの終了条件'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise の ID ベースのサービスとインフラストラクチャの条件を満たしていることを確認します。
ms.openlocfilehash: 49ba7801b740b2a1cfd77955517646ee80174712
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869603"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a>フェーズ 2: ID インフラストラクチャの終了条件

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

フェーズ 3 に進む前に、ID インフラストラクチャが次の条件を満たしていることを確認してください。また、ID インフラストラクチャのその他の推奨事項については、「[必要条件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)」を参照してください。

<a name="crit-identity-user-groups"></a>
## <a name="required-all-users-groups-and-group-memberships-have-been-created"></a>必須: すべてのユーザー、グループ、およびグループ メンバーシップが作成されている

次の目的でユーザー アカウントとグループを作成しています。

- 組織内の従業員、ベンダー、契約社員、または組織で勤務または組織に協力するパートナーが、Azure Active Directory (AD) で対応するユーザー アカウントを持っている。
- Azure AD のグループとそのメンバーに、さまざまな目的 (Microsoft クラウド サービスのセキュリティ設定のプロビジョニング、自動ライセンスなど) でユーザー アカウントとその他のグループが含まれている。

必要に応じて、[手順 1](identity-plan-users-groups.md) がこの必須条件を満たす上で役立ちます。

<a name="crit-identity-sync"></a>
## <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a>必須: ユーザーとグループが Azure AD と同期される

既存のオンプレミス ID プロバイダー (Windows Server Active Directory (AD) など) がある場合は、Azure AD Connect を使用して、オンプレミス ID プロバイダーから Azure AD テナントへユーザー アカウントとグループを同期しています。

ディレクトリ同期により、ユーザーは各自のコンピューターやオンプレミス リソースにサインインするときに使用する資格情報で、Office 365 やその他の Microsoft クラウド サービスにもサインインできます。

必要に応じて、[手順 7](identity-azure-ad-connect.md) がこの必須条件を満たすのに役立ちます。

この必須条件を省略した場合、ユーザー アカウントとグループの 2 つのセットが作成されています。

- オンプレミス ID プロバイダーに存在するユーザー アカウントとグループ
- Azure AD テナントに存在するユーザー アカウントとグループ

この状態では、IT 管理者とユーザーが、ユーザー アカウントとグループの 2 つのセットを手動で保守する必要があります。このため、アカウント、パスワード、グループが同期されていない状況が必然的に発生します。

### <a name="how-to-test"></a>テスト方法
オンプレミスの資格情報を使用した認証が正しく機能することを確認するには、オンプレミスの資格情報を使用して Office 365 ポータルにログインします。

ディレクトリ同期が正しく動作していることを確認するには、次の手順に従います。

1.  Windows Server AD で新しいテスト グループを作成します。
2.  同期時刻まで待ちます。
3.  Azure AD テナントを調べ、新しいテスト グループ名があることを確認します。

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a>必須: 全体管理者アカウントが保護されている 

Office 365 サブスクリプションの侵害の原因となる資格情報の侵害を防ぐため、[Office 365 全体管理者アカウントを保護しています](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560)。

この必須条件を省略した場合、全体管理者アカウントが攻撃および侵害を受けやすくなり、攻撃者は獲得攻撃、破壊、または身代金要求の目的で、システム全体でデータにアクセスできるようになります。

必要に応じて、[手順 2](identity-designate-protect-admin-accounts.md) がこの必須条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

全体管理者アカウントを保護していることを確認するには、次の手順を使用します。

1. PowerShell コマンド プロンプトで次の Azure AD V2 コマンドを実行します。専用の全体管理者アカウントだけが表示されます。
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. 手順 1 で表示された各アカウントを使用して Office 365 にサインインします。各サインインには多要素認証と、組織で使用可能なセカンダリ認証のうち最も強力なセカンダリ認証が必要です。

> [!Note]
> Azure AD V2 PowerShell モジュールのインストールと Office 365 へのサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>オプション: Office 365 のサインイン画面を組織に合わせてカスタマイズしている

「[クイック スタート: Azure AD のサインイン ページに会社のブランドを追加する](http://aka.ms/aadpaddbranding)」に従って組織のブランドを Office 365 サインイン ページに追加しています。

このオプション条件を省略した場合、ユーザーに対して汎用 Office 365 サインイン画面が表示され、ユーザーが当該組織のサイトにサインインすることを確信できない可能性があります。

必要に応じて、[手順 11](identity-customize-office-365-sign-in.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

アカウント名と多要素認証を使用して Office 365 ポータルにサインインします。カスタム ブランド要素がサインイン ページに表示されるはずです。

<a name="crit-identity-mfa"></a>
## <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a>オプション: ユーザーに対して多要素認証が有効になっている

「[Office 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)」と「[Office 365 ユーザー用の多要素認証を設定する](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)」に従い、ユーザー アカウントに対して多要素認証 (MFA) を有効にしています。

このオプション条件を省略した場合、ユーザー アカウントはサイバー攻撃による資格情報の侵害に対して脆弱になります。ユーザー アカウントのパスワードが侵害されると、そのアカウントのすべてのリソースと機能 (管理者ロールなど) を攻撃者が利用できるようになります。これにより、攻撃者は内部資料やその他のデータを複製、破壊、または身代金要求目的で保持することが可能になります。

必要に応じて、[手順 5](identity-multi-factor-authentication.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

1.  Office 365 Admin ポータルでテスト ユーザー アカウントを作成し、ライセンスを割り当てます。 
2.  実際のユーザー アカウントに使用している追加の検証方式 (電話へのメッセージの送信など) を使用して、テスト ユーザー アカウントの多要素認証を構成します。 
3.  テスト ユーザー アカウントを使用して Office 365 または Azure Portal にサインインします。
4.  MFA により、追加の確認情報を入力するように求められ、その結果認証が正常に完了することを確認します。 
5.  テスト ユーザー アカウントを削除します。

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a>オプション: ディレクトリ同期を監視している

「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」(パスワード同期の場合) または「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」(フェデレーテッド認証の場合) に従い、Azure AD Connect Health を展開しています。この展開では次の作業を行います。

- オンプレミスの各 ID サーバーに Azure AD Connect Health エージェントをインストールする。
- Azure AD Connect Health ポータルを使用して、継続的な同期の状態を監視する。

このオプション条件を省略した場合、クラウドベースの ID インフラストラクチャの状態をより正確に評価できます。

必要に応じて、[手順 8](identity-azure-ad-connect-health.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法
Azure AD Connect Health ポータルには、オンプレミス ID サーバーと継続的な同期の正確な最新の状態が表示されます。

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a>オプション: ユーザーが各自のパスワードをリセットできる

「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」に従って、ユーザーのパスワード リセットを構成しています。

この条件を満たしていない場合は、ユーザーはパスワードをリセットする際にユーザー アカウント管理者に依頼する必要があるため、追加の ID 管理オーバーヘッドが発生します。

必要に応じて、[手順 4](identity-password-reset.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

1. テスト ユーザー アカウントを作成し、初期パスワードを設定します。
2. 「[Office 365 でユーザーが自分のパスワードを再設定する](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a)」の手順に従って、テスト ユーザー アカウントのパスワードをリセットします。
3. サインアウトし、リセット後のパスワードを使用してテスト ユーザー アカウントにサインインします。
4. テスト ユーザー アカウントを削除します。

<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a>オプション: ユーザーに対してパスワードの書き戻しが有効になっている

「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」の手順に従い、Microsoft 365 Enterprise サブスクリプションの Azure AD テナントのパスワードの書き戻しを有効にしています。

このオプション条件を省略した場合、オンプレミスのネットワークに接続していないユーザーは、IT 管理者を通じて Windows Server AD のパスワードをリセットまたはロック解除する必要があります。

必要に応じて、[手順 9](identity-password-writeback.md) がこの必須条件を満たす上で役立ちます。

>[!Note]
>パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生するリスクが高いことが Azure AD により検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。
>

### <a name="how-to-test"></a>テスト方法

パスワードの書き戻しをテストするには、Office 365 でパスワードを変更します。各自のアカウントと新しいパスワードを使用して、オンプレミスの Windows Server AD リソースにアクセスできるはずです。

1. オンプレミスの Windows Server AD にテスト ユーザー アカウントを作成し、ディレクトリ同期を許可し、Office 365 管理ポータルで Office 365 ライセンスをこのテスト ユーザー アカウントに付与します。
2. オンプレミスの Windows Server AD ドメインに参加しているリモート コンピューターから、テスト ユーザー アカウントの資格情報を使用してコンピューターと Office 365 ポータルにサインインします。
3. **[設定] > [Office 365 の設定] > [パスワード] > [パスワードの設定]** を選択します。
4. 現在のパスワードを入力し、新しいパスワードを入力し、確認のため新しいパスワードをもう一度入力します。
5. Office 365 ポータルとリモート コンピューターからサインアウトし、テスト ユーザー アカウントと新しいパスワードを使用してコンピューターにサインインします。これにより、Azure AD テナントを使用して、オンプレミス Windows Server AD ユーザー アカウントのパスワードを変更できたことが証明されます。

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-single-sign-on"></a>オプション: ユーザーはシングル サインオンを使用してサインインできる

クラウドベースのアプリケーション (Office 365 など) へのユーザーのサインイン方法を組織が簡素化できるように、[Azure AD Connect: シームレス シングル サインオン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)を有効にしています。

このオプション条件を省略した場合、Azure AD を使用するその他のアプリケーションにユーザーがアクセスすると、ユーザーに対して資格情報の入力が求められることがあります。

必要に応じて、[手順 10](identity-single-sign-on.md) がこのオプション条件を満たすのに役立ちます。


<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>オプション: グループ メンバーシップに基づいてユーザー アカウントに対しライセンスを自動的に割り当てるか削除するグループベースのライセンス

Office 365 と EMS の両方のライセンスの割り当てと削除が自動的に実行されるようにするため、適切な Azure AD セキュリティ グループに対して[グループベースのライセンスを有効にしています](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。

このオプション条件を省略した場合、次の操作を手動で行う必要があります。

- Office 365 および EMS へのアクセス権を付与する予定の新しいユーザーにライセンスを割り当てる。
- 組織に所属していないユーザーや、Office 365 および EMS へのアクセス権がないユーザーからライセンスを削除する。

必要に応じて、[手順 12](identity-group-based-licensing.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

1. Azure Portal を使用して Azure AD にテスト セキュリティ グループを作成し、Office 365 と EMS のライセンスを割り当てるグループベースのライセンスを構成します。
2. Azure AD にテスト ユーザー アカウントを作成し、テスト セキュリティ グループに追加します。
3. Office 365 管理ポータルでこのユーザー アカウントのプロパティを調べ、このアカウントに Office 365 と EMS のライセンスが割り当てられていることを確認します。
4. テスト セキュリティ グループからテスト ユーザー アカウントを削除します。
5. このユーザー アカウントのプロパティを調べ、このアカウントに Office 365 と EMS のライセンスが割り当てられていないことを確認します。
6. テスト セキュリティ グループとテスト ユーザー アカウントを削除します。

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>オプション: 動的グループ メンバーシップの設定により、ユーザー アカウントの属性に基づいてユーザー アカウントがグループに自動的に追加される

Azure AD の動的グループを決定し、「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」の手順に従って、グループを作成し、グループ メンバーシップのユーザー アカウント属性と値を指定するルールを作成しています。

このオプション条件を省略した場合、新しいアカウントが追加されるか、またはユーザー アカウントの属性が時間の経過に伴って変化するときに、グループ メンバーシップを手動で設定する必要があります。たとえば、Sales 部門から Accounting 部門にユーザーが移動した場合、次の操作を行う必要があります。

- ユーザーの Departement 属性の値を更新する。
- Sales グループからユーザーを手動で削除する。
- Accounting グループにユーザーを手動で追加する。

Sales グループと Accounting グループが動的グループである場合は、必要な操作はユーザー アカウントの Department の値の変更だけです。

必要に応じて、[手順 15](identity-automatic-group-membership.md) がこのオプション条件を満たすのに役立ちます。

### <a name="how-to-test"></a>テスト方法

1. Azure Portal で Azure AD にテスト用の動的グループを作成し、Department が「test 1」であるというルールを構成します。
2. Azure AD でテスト ユーザー アカウントを作成し、Department プロパティに「test1」を設定します。
3. テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーになっていることを確認します。
4. テスト ユーザー アカウントの Department プロパティの値を「test2」に変更します。
5. テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーではないことを確認します。
6. テスト用の動的グループとテスト ユーザー アカウントを削除します。

<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>オプション: 特定の Azure AD セキュリティと Office 365 グループでセルフサービスによるグループの管理が有効になっている

セルフサービスによる管理に適しているグループを判別し、各グループの所有者に対してグループ管理のワークフローと責任を説明し、これらのグループに対して[Azure AD でのセルフサービスによる管理をセットアップ](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)しています。

このオプション条件を省略した場合、IT 管理者がすべての Azure AD グループ管理タスクを手動で実行する必要があります。

必要に応じて、[手順 14](identity-self-service-group-management.md) がこのオプション条件を満たす上で役立ちます。

### <a name="how-to-test"></a>テスト方法
1.  Azure Portal で Azure AD にテスト ユーザー アカウントを作成します。
2.  テスト ユーザー アカウントとしてサインインし、テスト Azure AD セキュリティ グループを作成します。
3.  サインアウトして、IT 管理者アカウントでサインインします。
4.  テスト セキュリティ グループで、テスト ユーザー アカウントをセルフサービスにより管理するように構成します。
5.  サインアウトし、テスト ユーザー アカウントでサインインします。
6.  Azure Portal を使用して、テスト セキュリティ グループにメンバーを追加します。
7.  テスト セキュリティ グループとテスト ユーザー アカウントを削除します。

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a>オプション: 資格情報を侵害から保護するため、Azure AD Identity Protection が有効になっている

次の目的で Azure AD Identity Protection を有効にしています。

- 潜在的な ID の脆弱性に対処する。
- 資格情報の侵害の疑いがあるものを検出する。
- 発生している不審な ID インシデントを調査して対処する。

このオプション条件を省略した場合、資格情報の侵害を試みる操作の検出または自動的な防止、ID 関連のセキュリティ インシデントの調査を実行できません。その結果、資格情報の侵害に対して組織が脆弱になり、組織の機密データに対する脅威が生じます。

必要に応じて、[手順 6](identity-azure-ad-identity-protection.md) がこのオプション条件を満たすのに役立ちます。

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>オプション: 全体管理者ロールをオンデマンドで割り当てることができるように、Privileged Identity Management をセットアップしている

「[Azure AD Privileged Identity Management とは](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」の手順に従い Azure AD テナントで PIM を有効にしており、全体管理者アカウントを適格な管理者として構成しています。

また、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」の推奨事項に従って、サイバー攻撃者から特権アクセスを保護するロードマップを策定しています。

このオプション条件を省略した場合、全体管理者アカウントが継続的なオンライン攻撃の対象となり、このアカウントが侵害された場合には、攻撃者が機密情報の獲得、破壊、または身代金要求の目的で保持することができるようになります。

必要に応じて、[手順 3](identity-azure-ad-identity-protection.md) がこのオプション条件を満たすのに役立ちます。


## <a name="next-phase"></a>次のフェーズ

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| Microsoft 365 Enterprise のエンドツーエンド展開プロセスの次のフェーズは、[Windows 10 Enterprise](windows10-infrastructure.md)です。 |

