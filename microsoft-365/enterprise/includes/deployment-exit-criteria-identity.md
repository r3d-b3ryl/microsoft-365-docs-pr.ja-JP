ID インフラストラクチャに関する追加の推奨事項については、[前提条件](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)も参照してください。

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a>必須: 全体管理者アカウントが保護されている 

[Office 365 全体管理者アカウントが保護される](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)ことで、Microsoft 365 サブスクリプションの侵害につながる可能性がある攻撃者による資格情報の侵害を阻止します。

この必須条件を省略した場合、全体管理者アカウントが攻撃および侵害を受けやすくなり、攻撃者は獲得攻撃、破壊、または身代金要求の目的で、システム全体でデータにアクセスできるようになります。

必要に応じて、[手順 1](../identity-create-protect-global-admins.md#identity-global-admin) がこの必須条件を満たす上で役立ちます。

#### <a name="how-to-test"></a>テスト方法

全体管理者アカウントを保護していることを確認するには、次の手順を使用します。

1. PowerShell コマンドプロンプトで、次の Azure Active Directory PowerShell for Graph コマンドを実行します。 専用のグローバル管理者アカウントのリストのみが表示されます。
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. 手順 1 の各アカウントを使用して、Office 365 にサインインします。 それぞれのサインインでは、Azure 多要素認証および組織で使用できる最も強力な2 次認証が必要です。

> [!Note]
> Azure Active Directory PowerShell for Graph モジュールのインストールと Office 365 へのサインインの手順については、「[Office 365 PowerShell への接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>オプション: 全体管理者ロールをオンデマンドで割り当てることができるように、Privileged Identity Management をセットアップしている

「[Azure AD Privileged Identity Management (PIM) とは](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)」の手順を実行して、Azure AD テナントで PIM を有効にし、全体管理者アカウントを適格な管理者として構成しています。

また、「[Azure AD でのハイブリッドおよびクラウド デプロイ用の特権アクセスをセキュリティで保護する](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)」の推奨事項に従って、サイバー攻撃者から特権アクセスを保護するロードマップを策定しています。

このオプション条件を省略した場合、全体管理者アカウントが継続的なオンライン攻撃の対象となり、このアカウントが侵害された場合には、攻撃者が機密情報の獲得、破壊、または身代金要求の目的で保持することができるようになります。

必要に応じて、[手順 1](../identity-create-protect-global-admins.md#identity-pim) がこのオプション条件を満たす上で役立ちます。

<a name="crit-identity-pam"></a>
### <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>省略可能: 特権アクセス管理を Office 365 で構成している

[Office 365 での特権アクセス管理を設定する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)トピックにある情報を使用して、特権アクセスを有効にし、組織内に 1 つまたは複数の特権アクセス ポリシーを作成しました。 これらのポリシーを構成して、機密データへのアクセスや重要な構成設定へのアクセスのために just-in-time アクセスが有効にされました。

必要に応じて、[手順 1](../identity-create-protect-global-admins.md#identity-pam) がこの必須条件を満たす上で役立ちます。 

<a name="crit-password-prot"></a>
### <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>省略可能: Azure AD パスワード保護により、脆弱なパスワードの使用が禁止されている

グローバル禁止パスワードとカスタムの用語 (省略可能) に対応する形で、[クラウド内](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)、および [オンプレミス Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) に対する脆弱なパスワードの禁止を有効にしています。

必要に応じて、[手順 2](../identity-secure-your-passwords.md#identity-password-prot) がこのオプション条件を満たす上で役立ちます。

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a>オプション: ユーザーが各自のパスワードをリセットできる

「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」に従って、ユーザーのパスワード リセットを構成しています。

この条件を満たしていない場合は、ユーザーはパスワードをリセットする際にユーザー アカウント管理者に依頼する必要があるため、追加の ID 管理オーバーヘッドが発生します。

必要に応じて、[手順 2](../identity-secure-your-passwords.md#identity-pw-reset) がこのオプション条件を満たす上で役立ちます。

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>オプション: ユーザーは Azure AD シームレス シングル サインオンを使用してサインインできます

クラウドベースのアプリケーション (Office 365 など) へのユーザーのサインイン方法を組織が簡素化できるように、[Azure AD Connect: シームレス シングル サインオン](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)を有効にしています。

このオプション条件を省略した場合、Azure AD テナントを使用する他のアプリケーションにユーザーがアクセスすると、ユーザーに対して資格情報の入力が求められることがあります。

必要に応じて、[手順 2](../identity-secure-your-passwords.md#identity-sso) がこのオプション条件を満たす上で役立ちます。

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>オプション: Office 365 のサインイン画面を組織に合わせてカスタマイズしている

「[クイック スタート: Azure AD のサインイン ページに会社のブランドを追加する](https://aka.ms/aadpaddbranding)」に従って組織のブランドを Office 365 サインイン ページに追加しています。

このオプション条件を省略した場合、ユーザーに対して汎用 Office 365 サインイン画面が表示され、ユーザーが当該組織のサイトにサインインすることを確信できない可能性があります。

必要に応じて、[手順 2](../identity-secure-your-passwords.md#identity-custom-sign-in) がこのオプション条件を満たす上で役立ちます。


<a name="crit-identity-mfa"></a>
### <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>オプション: ユーザーに対して Azure 多要素認証が有効になっている

「[Azure 多要素認証の計画](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)」と「[条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)」を使用して、ユーザー アカウントのAzure 多要素認証 (MFA) を有効にしています。

このオプション条件を省略した場合、ユーザー アカウントはサイバー攻撃による資格情報の侵害に対して脆弱になります。ユーザー アカウントのパスワードが侵害されると、そのアカウントのすべてのリソースと機能 (管理者ロールなど) を攻撃者が利用できるようになります。これにより、攻撃者は内部資料やその他のデータを複製、破壊、または身代金要求目的で保持することが可能になります。

必要に応じて、[手順 3](../identity-secure-user-sign-ins.md#identity-mfa) がこのオプション条件を満たす上で役立ちます。

#### <a name="how-to-test"></a>テスト方法

1.  テスト ユーザー アカウントを作成して、それらにライセンスを割り当てます。 
2.  実際のユーザー アカウントに使用している (電話へのテキスト メッセージの送信など) 追加の検証方式を使用して、テスト ユーザー アカウントの Azure 多要素認証を構成します。 
3.  テスト ユーザー アカウントを使用して Office 365 ポータルにサインインします。
4.  MFA により、追加の確認情報を入力するように求められ、その結果認証が正常に完了することを確認します。 
5.  テスト ユーザー アカウントを削除します。

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a>省略可能: 資格情報を侵害から保護するために Azure AD Identity Protection が有効化されている (Microsoft 365 Enterprise E5 のみ)

次の目的で Azure AD Identity Protection を有効にしています。

- 潜在的な ID の脆弱性に対処する。
- 資格情報の侵害の疑いがあるものを検出する。
- 発生している不審な ID インシデントを調査して対処する。

このオプション条件を省略した場合、資格情報の侵害を試みる操作の検出または自動的な防止、ID 関連のセキュリティ インシデントの調査を実行できません。その結果、資格情報の侵害に対して組織が脆弱になり、組織の機密データに対する脅威が生じます。

必要に応じて、[手順 3](../identity-secure-user-sign-ins.md#identity-ident-prot) がこのオプション条件を満たす上で役立ちます。


#### <a name="how-to-test"></a>テスト方法

1. テスト ユーザー アカウントを作成し、初期パスワードを設定します。
2. 「[Office 365 でユーザーが自分のパスワードを再設定する](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords)」の手順に従って、テスト ユーザー アカウントのパスワードをリセットします。
3. サインアウトし、リセット後のパスワードを使用してテスト ユーザー アカウントにサインインします。
4. テスト ユーザー アカウントを削除します。

<a name="crit-identity-sync"></a>
### <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>ハイブリッド アイデンティティの場合必須: ユーザーとグループが Azure AD と同期されている

既存のオンプレミス Active Directory Domain Services (AD DS) がある場合は、Azure AD Connect を使用して、オンプレミス AD DS から Azure AD テナントへユーザー アカウントとグループを同期しています。

ディレクトリ同期により、ユーザーは各自のコンピューターやオンプレミス リソースにサインインするときに使用する資格情報で、Office 365 やその他の Microsoft クラウド サービスにもサインインできます。

必要に応じて、[手順 4](../identity-add-user-accounts.md#identity-sync) がこの必須条件を満たす上で役立ちます。

この必須条件を省略した場合、2 つのセットのユーザー アカウントとグループが作成されます。

- オンプレミス AD DS に存在するユーザー アカウントとグループ
- Azure AD テナントに存在するユーザー アカウントとグループ

この状態では、IT 管理者とユーザーが、ユーザー アカウントとグループの 2 つのセットを手動で保守する必要があります。このため、アカウント、パスワード、グループが同期されていない状況が必然的に発生します。

#### <a name="how-to-test"></a>テスト方法
オンプレミスの資格情報を使用した認証が正しく機能することを確認するには、オンプレミスの資格情報を使用して Office ポータルにログインします。

ディレクトリ同期が正しく動作していることを確認するには、次の手順に従います。

1.  AD DS で新しいテスト グループを作成します。
2.  同期時刻まで待ちます。
3.  Azure AD テナントを調べ、新しいテスト グループ名があることを確認します。

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a>オプション: ディレクトリ同期を監視している

「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」(パスワード同期の場合) または「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」(フェデレーテッド認証の場合) に従い、Azure AD Connect Health を展開しています。この展開では次の作業を行います。

- オンプレミスの各 ID サーバーに Azure AD Connect Health エージェントをインストールする。
- Azure AD Connect Health ポータルを使用して、継続的な同期の状態を監視する。

このオプション条件を省略した場合、クラウドベースの ID インフラストラクチャの状態をより正確に評価できます。

必要に応じて、[手順 4](../identity-add-user-accounts.md#identity-sync-health) がこのオプション条件を満たす上で役立ちます。

#### <a name="how-to-test"></a>テスト方法
Azure AD Connect Health ポータルには、オンプレミス ドメイン コントローラーと継続中の同期の正確な現在の状態が表示されます。


<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a>オプション: ユーザーに対してパスワードの書き戻しが有効になっている

「[Azure AD のセルフ サービスによるパスワード リセットの迅速なデプロイ](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)」の手順に従い、Microsoft 365 Enterprise サブスクリプションの Azure AD テナントのパスワードの書き戻しを有効にしています。

このオプション条件を省略した場合、オンプレミスのネットワークに接続していないユーザーは、IT 管理者を通じて AD DS のパスワードをリセットまたはロック解除する必要があります。

必要に応じて、[手順 4](../identity-add-user-accounts.md#identity-pw-writeback) がこのオプション条件を満たす上で役立ちます。

>[!Note]
>パスワードの書き戻しは、Azure AD Identity Protection 機能 (アカウント侵害が発生するリスクが高いことが Azure AD により検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。
>

#### <a name="how-to-test"></a>テスト方法

パスワードの書き戻しをテストするには、Office 365 でパスワードを変更します。 オンプレミス AD DS リソースにアクセスするには、自分のアカウントと新しいパスワードを使用できるようする必要があります。

1. オンプレミスの AD DS にテスト ユーザー アカウントを作成し、ディレクトリ同期を実行して、Microsoft 365 管理センターで Microsoft 365 Enterprise ライセンスをそのテスト ユーザー アカウントに付与します。
2. オンプレミスの AD DS ドメインに参加しているリモート コンピューターから、テスト ユーザー アカウントの資格情報を使用してコンピューターと Office ポータルにサインインします。
3. **[設定] > [Office 365 の設定] > [パスワード] > [パスワードの設定]** を選択します。
4. 現在のパスワードを入力し、新しいパスワードを入力し、確認のため新しいパスワードをもう一度入力します。
5. Office ポータルとリモート コンピューターからサインアウトし、テスト ユーザー アカウントと新しいパスワードを使用してコンピューターにサインインします。 Azure AD テナントを使用したオンプレミスの AD DS のユーザー アカウントパスワードを変更することができたことが、これで証明されます。

#### <a name="how-to-test"></a>テスト方法

ユーザーのアカウント名と Azure 多要素認証を使用して、Office 365 ポータルにサインインします。 サインイン ページにカスタムのブランド化要素が表示されます。


<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>オプション: 特定の Azure AD セキュリティと Office 365 グループでセルフサービスによるグループの管理が有効になっている

セルフサービスによる管理に適しているグループを判別し、各グループの所有者に対してグループ管理のワークフローと責任を説明し、これらのグループに対して[Azure AD でのセルフサービスによる管理をセットアップ](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)しています。

このオプション条件を省略した場合、IT 管理者がすべての Azure AD グループ管理タスクを手動で実行する必要があります。

必要に応じて、[手順 5](../identity-use-group-management.md#identity-self-service-groups) がこのオプション条件を満たすのに役立ちます。

#### <a name="how-to-test"></a>テスト方法
1.  Azure Portal で Azure AD にテスト ユーザー アカウントを作成します。
2.  テスト ユーザー アカウントとしてサインインし、テスト Azure AD セキュリティ グループを作成します。
3.  サインアウトして、IT 管理者アカウントでサインインします。
4.  テスト セキュリティ グループで、テスト ユーザー アカウントをセルフサービスにより管理するように構成します。
5.  サインアウトし、テスト ユーザー アカウントでサインインします。
6.  Azure Portal を使用して、テスト セキュリティ グループにメンバーを追加します。
7.  テスト セキュリティ グループとテスト ユーザー アカウントを削除します。

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>オプション: 動的グループ メンバーシップの設定により、ユーザー アカウントの属性に基づいてユーザー アカウントがグループに自動的に追加される

Azure AD の動的グループを決定し、「[Azure Active Directory で動的グループ メンバーシップの属性ベースのルールを作成する](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)」の手順に従って、グループを作成し、グループ メンバーシップのユーザー アカウント属性と値を指定するルールを作成しています。

このオプション条件を省略した場合、新しいアカウントが追加されるか、またはユーザー アカウントの属性が時間の経過に伴って変化するときに、グループ メンバーシップを手動で設定する必要があります。たとえば、Sales 部門から Accounting 部門にユーザーが移動した場合、次の操作を行う必要があります。

- ユーザーの Departement 属性の値を更新する。
- Sales グループからユーザーを手動で削除する。
- Accounting グループにユーザーを手動で追加する。

Sales グループと Accounting グループが動的グループである場合は、必要な操作はユーザー アカウントの Department の値の変更だけです。

必要に応じて、[手順 5](../identity-use-group-management.md#identity-dyn-groups) がこのオプション条件を満たすのに役立ちます。

#### <a name="how-to-test"></a>テスト方法

1. Azure Portal で Azure AD にテスト用の動的グループを作成し、Department が「test 1」であるというルールを構成します。
2. Azure AD でテスト ユーザー アカウントを作成し、Department プロパティに「test1」を設定します。
3. テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーになっていることを確認します。
4. テスト ユーザー アカウントの Department プロパティの値を「test2」に変更します。
5. テスト ユーザー アカウントのプロパティを調べ、このアカウントがテスト用の動的グループのメンバーではないことを確認します。
6. テスト用の動的グループとテスト ユーザー アカウントを削除します。

<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>オプション: グループ メンバーシップに基づいてユーザー アカウントに対しライセンスを自動的に割り当てるか削除するグループベースのライセンス

Microsoft 365 Enterprise ライセンスを自動的に割り当てたり、未割り当てにしたりするため、適切な Azure AD セキュリティ グループの[グループベースのライセンスを有効にしています](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。

このオプション条件を省略した場合、次の操作を手動で行う必要があります。

- アクセス権を付与する予定の新しいユーザーにライセンスを割り当てます。
- 組織に所属していないユーザーや、アクセス権がないユーザーへのライセンスの割り当てを解除します。

必要に応じて、[手順 5](../identity-use-group-management.md#identity-group-license) がこのオプション条件を満たすのに役立ちます。

#### <a name="how-to-test"></a>テスト方法

1. Azure ポータルを使用して Azure AD にテスト セキュリティ グループを作成し、Microsoft 365 Enterprise ライセンスを割り当てるためにグループベースのライセンスを構成します。
2. テスト ユーザー アカウントを Azure AD に作成して、このアカウントをテスト セキュリティ グループに追加します。
3. Microsoft 365 管理センターでユーザー アカウントのプロパティを調査し、そのアカウントに Microsoft 365 Enterprise ライセンスが割り当てられていることを確認します。
4. テスト セキュリティ グループからテスト ユーザー アカウントを削除します。
5. ユーザー アカウントのプロパティを調べて、そのアカウントに Microsoft 365 Enterprise ライセンスが割り当てられていないことを確認します。
6. テスト セキュリティ グループとテスト ユーザー アカウントを削除します。


<a name="crit-identity-access-reviews"></a>
### <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>省略可能: アクセスを監視するために構成して使用されるアクセス ビュー

グループ メンバーシップ、エンタープライズ アプリケーションへのアクセス、ロールの割り当てを監視するためのさまざまな種類のアクセス レビューを構成するために、これらの記事を使用しました。

- [グループとアプリ](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD ロール](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure リソース ロール](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

必要に応じて、[手順 6](../identity-configure-identity-governance.md#identity-access-reviews)がこのオプション条件を満たすのに役立ちます。
