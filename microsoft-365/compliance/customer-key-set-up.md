---
title: 顧客キーの設定
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定する方法についてMicrosoft 365。
ms.openlocfilehash: f3d7da27e0c9a5e27f0c3e7bcc3adb48dad5d42c
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634517"
---
# <a name="set-up-customer-key"></a>顧客キーの設定

顧客キーを使用すると、組織の暗号化キーを制御し、microsoft のデータ センターで保存されているデータMicrosoft 365を使用してデータを暗号化する方法を構成します。 つまり、顧客キーを使用すると、顧客は自分のキーを使用して、自分に属する暗号化の層を追加できます。

顧客キーを使用する前に Azure をOffice 365。 この記事では、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、次に、Azure リソースで顧客キーを設定する手順Office 365。 Azure を設定した後で、組織内のさまざまなワークロード間でデータを暗号化するために割り当てるポリシーと、どのキーを割り当てるMicrosoft 365決定します。 顧客キーの詳細、または一般的な概要については、「顧客キーを使用したサービスの暗号化」を参照[Office 365。](customer-key-overview.md)
  
> [!IMPORTANT]
> この記事のベスト プラクティスに従ってください。 これらは TIP および IMPORTANT として呼 **び** 出 **されます**。 顧客キーを使用すると、組織全体と同じ規模のスコープを持つルート暗号化キーを制御できます。 つまり、これらのキーの間違いは大きな影響を与え、サービスの中断やデータの取り消しできない損失を引き起こす可能性があります。
  
## <a name="before-you-set-up-customer-key"></a>顧客キーを設定する前に

開始する前に、組織に適切な Azure サブスクリプションとライセンスを持っている必要があります。 有料の Azure サブスクリプションを使用するには、Enterprise Agreementまたはクラウド サービス プロバイダーを使用します。 クレジット カードベースの支払いは受け付けておかねない。 請求に必要なアカウントを承認して設定します。 無料、試用版、スポンサーシップ、MSDN サブスクリプション、および従来のサポートで取得したサブスクリプションは対象外です。

Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 Compliance、Microsoft 365 E5 Information Protection &ガバナンス SKU はカスタマー キーを提供します。 Office 365 Advanced Compliance SKU は、新しいライセンスの調達に使用できなくなりました。 既存のOffice 365 Advanced Complianceライセンスは引き続きサポートされます。

この記事の概念と手順を理解するには、Azure のドキュメントを[Key Vault](/azure/key-vault/)してください。 また、Azure で使用される用語 (テナントなど) [をAzure ADしてください](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。
  
ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティング サービス (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。 ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、および視点をユーザーに customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>顧客キーを設定する手順の概要

顧客キーを設定するには、これらのタスクを一覧表示された順序で実行します。 この記事の残りの部分では、各タスクの詳細な手順を説明するか、プロセスの各ステップの詳細情報にリンクします。
  
**Azure と Azure のMicrosoft FastTrack:**
  
これらのタスクのほとんどを完了するには、リモートでユーザーに接続Azure PowerShell。 最適な結果を得る場合は、バージョン 4.4.0 以降を使用Azure PowerShell。
  
- [2 つの新しい Azure サブスクリプションを作成する](#create-two-new-azure-subscriptions)

- [顧客キーをアクティブ化する要求を送信Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [必須の保持期間を使用するように Azure サブスクリプションを登録する](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  この登録プロセスの完了には 5 営業日かかります。

- [各サブスクリプションにプレミアム Azure Key Vaultを作成する](#create-a-premium-azure-key-vault-in-each-subscription)

- [各キー コンテナーにアクセス許可を割り当てる](#assign-permissions-to-each-key-vault)

- [キー コンテナーでソフト削除が有効になっているか確認する](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [キーを作成またはインポートして、各キー コンテナーにキーを追加する](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [キーの回復レベルを確認する](#check-the-recovery-level-of-your-keys)

- [Azure のバックアップ Key Vault](#back-up-azure-key-vault)

- [Azure の構成Key Vault検証する](#validate-azure-key-vault-configuration-settings)

- [Azure の各キーの URI をKey Vaultする](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure Key Vaultおよび顧客Microsoft FastTrackのタスクを完了する

Azure Key Vault でこれらのタスクを実行します。 顧客キーで使用するすべての DEP に対して、以下の手順を実行する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

顧客キーには、2 つの Azure サブスクリプションが必要です。 ベスト プラクティスとして、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。 Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織で使用されるのと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。 たとえば、組織でグローバル管理者特権を持つ仕事用または学校用のアカウントを使用します。 詳細な手順については、「 [組織として Azure にサインアップする」を参照してください](/azure/active-directory/fundamentals/sign-up-organization)。
  
> [!IMPORTANT]
> 顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。 これらの Azure サブスクリプションを使用して、ユーザーの暗号化キーを管理Office 365。 これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。

組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。 これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>顧客キーをアクティブ化する要求を送信Office 365

2 つの新しい Azure サブスクリプションを作成したら、適切なカスタマー キーオファー要求をポータルでMicrosoft FastTrack[があります](https://fasttrack.microsoft.com/)。 組織内の承認された指定に関してオファー フォームで行う選択は重要であり、顧客キー登録の完了に必要です。 組織内で選択された役割の役員は、顧客キーデータ暗号化ポリシーで使用されるすべてのキーを取り消して破棄する要求の信頼性を保証します。 組織で使用するカスタマー キー DEP の種類ごとに、この手順を 1 回実行する必要があります。

**顧客FastTrackチームは顧客キーのサポートを提供しない。Office 365は、FastTrackポータルを使用してフォームを送信し、顧客キーの関連するオファーを追跡するのに役立ちます。要求を送信したらFastTrack対応する顧客キーオンボーディング チームに連絡して、オンボーディング プロセスを開始します。**
  
顧客キーをアクティブ化するオファーを送信するには、次の手順を実行します。
  
1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、ポータルに[サインインMicrosoft FastTrackします](https://fasttrack.microsoft.com/)。

2. ログインしたら、適切なドメインを選択します。

3. 選択したドメインで、 **上部のナビゲーション** バーから [サービスの要求] を選択し、利用可能なオファーの一覧を確認します。

4. 該当するオファーの情報カードを選択します。

   - **複数のMicrosoft 365ワークロード:** [暗号化キーの要求] のヘルプを **選択Microsoft 365** します。

   - **Exchange OnlineとSkype for Business:** [暗号化キーの要求] のヘルプを **選択** Exchangeします。

   - **SharePoint、OneDrive、Teamsファイル:** [暗号化キーの要求] ヘルプを選択して、SharePoint **および** OneDrive for Businessします。

5. オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。

6. オファー フォームに該当する詳細情報と要求された情報を入力します。 暗号化キーとデータの永続的で不可逆的な破壊を承認するために承認する組織の役員の選択に特に注意を払います。 フォームが完成したら、[送信] を選択 **します**。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>必須の保持期間を使用するように Azure サブスクリプションを登録する

ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。 このため、Customer Key で使用されるリソースには強力な保護が必要です。 Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。 必須の保持期間に対して Azure サブスクリプションにタグ *を付けまたは登録できます*。 必須の保持期間によって、Azure サブスクリプションの即時および取り消し不可の取り消しが防止されます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、管理者チームとのMicrosoft 365必要です。 このプロセスの完了には 5 営業日かかります。 以前は、必須の保持期間を "キャンセルしない" と呼ばれる場合があります。
  
チームに連絡するMicrosoft 365、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。 開始する前に、[Azure PowerShell Az](/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。
  
1. サインインするには、Azure PowerShell。 手順については、「サインインする[」を参照Azure PowerShell](/powershell/azure/authenticate-azureps)。

2. 必須の保持Register-AzProviderFeature使用するために、サブスクリプションを登録するには、Register-AzProviderFeature コマンドレットを実行します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスを完了するには、Microsoft にお問い合わせください。

   - 個々のメールボックスに DEP を割り当てる顧客キーを有効Exchange Onlineに問い[合 exock@microsoft.com](mailto:exock@microsoft.com)。

   - すべてのテナント ユーザーの SharePoint Online および OneDrive for Business コンテンツ (Teams ファイルを含む) を暗号化するために DEP を割り当てる顧客キーを有効にする場合は、spock@microsoft.com [に問い合 spock@microsoft.com](mailto:spock@microsoft.com)。

   - すべてのテナント ユーザーに対して複数の Microsoft 365 ワークロード (Exchange Online、Teams、Microsoft Information Protection) でコンテンツを暗号化するために DEP を割り当てる顧客キーを有効にする場合は、m365-ck@service.microsoft.com に[問い合 m365-ck@service.microsoft.com](mailto:m365-ck@service.microsoft.com)。

   - メールに次の情報を含める。

     **件名**: 顧客キー \<*Your tenant's fully qualified domain name*\>

     **本文**: 必須の保持期間を完了するサブスクリプションの Get-AzProviderFeatureを含める。

     このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。

4. 登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 確認された場合、Get-AzProviderFeatureコマンドは、 **Registration State プロパティの [登録済** み] **の値を返** します。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure Key Vaultを作成する

キー コンテナーを作成する手順は[、はじめに と Azure Key Vault](/azure/key-vault/general/overview) に記載されています。この手順では、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内でのキー コンテナーの作成を説明します。
  
キー コンテナーを作成する場合は、SKU (標準または標準) を選択プレミアム。 Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、プレミアム SKU では、Key Vault キーの保護のために HSM を使用できます。 顧客キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、MICROSOFT では、SKU の一部のみを使用プレミアム強く推奨しています。 どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。 詳細については[Key Vault価格を](https://azure.microsoft.com/pricing/details/key-vault/)参照してください。
  
> [!IMPORTANT]
> 実稼働データプレミアム SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。
  
顧客キー Microsoft 365使用するサービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。 たとえば、カスタマー キーで Exchange Online、SharePoint Online、および複数ワークロードのシナリオで DEP を使用するには、3 組のキー コンテナーを作成します。
  
コンテナーを関連付ける DEP の使用目的を反映するキー コンテナーの名前付け規則を使用します。 名前付け規則の推奨事項については、以下の「ベスト プラクティス」セクションを参照してください。
  
データ暗号化ポリシーごとに、ペアにされた個別のコンテナー セットを作成します。 たとえばExchange Onlineポリシーをメールボックスに割り当てるときに、データ暗号化ポリシーのスコープが選択されます。 メールボックスには 1 つのポリシーのみを割り当て、最大 50 のポリシーを作成できます。 オンライン ポリシーのSharePointには、地理的な場所または地理的な場所にある組織内のすべてのデータが含 _まれます_。 複数ワークロード ポリシーのスコープには、すべてのユーザーでサポートされているワークロード全体のすべてのデータが含まれます。

キー コンテナーの作成には Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (小さい場合も含む) と Key Vault ログ記録 (有効な場合) も格納されたデータが生成されます。 ベスト プラクティスとして、Microsoft は個別の管理者を使用して各リソース グループを管理し、関連する顧客キー リソースを管理する一連の管理者に対応した管理を推奨します。
  
> [!IMPORTANT]
> 可用性を最大化するには、Microsoft 365 サービスの近くの地域にキー コンテナーを配置します。たとえば、Exchange Online 組織が 北米 にある場合は、キー コンテナーを 北米 に配置します。 組織がExchange Onlineしている場合は、キー コンテナーをヨーロッパに配置します。
>
> キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用と範囲の省略形を含める (たとえば、北米 に格納される Contoso SharePoint サービスの場合、名前の可能なペアは Contoso-CK-SP-NA-VaultA1 と Contoso-CK-SP-NA-VaultA2 です。 コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。 2017 年 7 月現在、コンテナー名は変更できません。ベスト プラクティスは、セットアップの計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。
>
> 可能であれば、ペア以外の領域にコンテナーを作成します。 ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。 したがって、地域のペアは、互いにバックアップ領域と見なされます。 つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。 このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。 ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。 可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。 これは、可用性の合計 4 つの地域の恩恵を受ける。 詳細については、「 [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。
  
### <a name="assign-permissions-to-each-key-vault"></a>各キー コンテナーにアクセス許可を割り当てる

実装に応じて、キー コンテナーごとに 3 つのアクセス許可セットを定義する必要があります。 たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。
  
- **組織のキー** コンテナーの毎日の管理を行うキー コンテナー管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。

  > [!IMPORTANT]
  > キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。 これは意図的で重要なプラクティスです。 暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。 ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。 代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。
  
  これらのアクセス許可を組織内のユーザーに割り当てるには、Azure サブスクリプションにサインインし、Azure PowerShell。 手順については、「サインインする[」を参照Azure PowerShell](/powershell/azure/authenticate-azureps)。

- 必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Azure コンテナー自体に** 対するアクセス許可を変更できる主要Key Vault寄稿者。 従業員がチームを離れるか、チームに参加する場合は、これらのアクセス許可を変更する必要があります。 キー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、アクセス許可を変更する必要があります。 この一連のキー コンテナー投稿者には、キー コンテナーの **共同作成者** ロールを付与する必要があります。 このロールは、Azure サーバーを使用して割り当Resource Manager。 詳細な手順については、「[Use Role-Based Access Control Azure サブスクリプション リソースへのアクセスを管理する」を参照してください](/azure/active-directory/role-based-access-control-configure)。 サブスクリプションを作成する管理者は、暗黙的にこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。

- 顧客 **キー Microsoft 365** 使用するキー コンテナーごとにアプリケーションを管理するためのアクセス許可は、wrapKey、unwrapKey、および対応する Microsoft 365 サービス プリンシパルへのアクセス許可を取得する必要があります。 

  サービス プリンシパルへのアクセスMicrosoft 365するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   ここで、

   - *コンテナー名* は、作成したキー コンテナーの名前です。
   - アプリExchange OnlineとSkype for Business、*appID をOffice 365に置き換* える`00000002-0000-0ff1-ce00-000000000000`
   - [オンラインSharePoint、OneDrive for Business、Teamsファイルの場合は、*appID Office 365置き換* える`00000003-0000-0ff1-ce00-000000000000`
   - すべてのテナント ユーザーに適用されるマルチワークロード ポリシー (Exchange、Teams、Microsoft Information Protection) の場合は、*appID をOffice 365に置き換* えてください。`c066d759-24ae-40e7-a56f-027002b5d3e4`

  例: ユーザーとユーザーのアクセス許可Exchange Online設定Skype for Business。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  例: オンラインファイル、SharePointファイル、OneDrive for BusinessファイルTeams設定します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>キー コンテナーでソフト削除が有効になっているか確認する

キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。 顧客キーでキーを使用する前に、Soft Delete と呼ばれるこの構成を有効にします。 Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。
  
キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。
  
1. Azure サブスクリプションにサインインするには、Windows PowerShell。 手順については、「サインインする[」を参照Azure PowerShell](/powershell/azure/authenticate-azureps)。

2. [Get-AzKeyVault コマンドレットを実行](/powershell/module/az.keyvault/get-azkeyvault)します。 この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。 キー コンテナーに対してソフト削除が適切に構成されている場合、 _Soft Delete Enabled_ プロパティは True の値を返 **します**。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートして、各キー コンテナーにキーを追加する

Azure Key Vault にキーを追加する方法は 2 Key Vault、またはキーをインポートできます。 キーを直接作成Key Vault、キーをインポートすると、キーの生成方法を完全に制御できます。 RSA キーを使用します。 Azure Key Vaultは、楕円曲線キーを使用したラップとアンラップはサポートされていません。
  
キー コンテナーにキーを直接作成するには、 [次のように Add-AzKeyVaultKey コマンドレット](/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

ここで、

- *コンテナー名* は、キーを作成するキー コンテナーの名前です。

- *キー名* は、新しいキーを指定する名前です。

  > [!TIP]
  > キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。 この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。
  
キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値として HSM を指定し、それ以外の場合は **[ソフトウェア**] を指定します。

例:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

キーをキー コンテナーに直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。
  
一部の組織では、キーの証明を確立するためにこのアプローチを好み、次の構成証明も提供します。
  
- インポートに使用されるツールセットには、生成するキーの暗号化に使用されるキー Exchange キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の HSM 内で生成される nCipher からの構成証明が含まれます。

- ツールセットには、nCipher によって製造された正規の HSM でも Azure Key Vaultセキュリティの世界が生成されたという nCipher からの構成証明が含まれています。 この構成証明は、Microsoft が本物の nCipher ハードウェアも使用しているという証明です。

セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。 キーをオンプレミスで作成してキー コンテナーにインポートする詳細な手順については、「Azure Key Vault の HSM で保護されたキーを生成および転送[する方法」を参照してください](/azure/key-vault/keys/hsm-protected-keys)。 Azure の手順を使用して、各キー コンテナーにキーを作成します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。 サブスクリプションの設定を確認するには、キーの回復レベルを確認します。
  
キーの回復レベルを確認するには、次Azure PowerShell、Get-AzKeyVaultKeyコマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、サブスクリプションを [キャンセルしない] リストに入れ、各キー コンテナーでソフト削除が有効になっていることを確認します。
  
### <a name="back-up-azure-key-vault"></a>Azure のバックアップ Key Vault

作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。 オフライン コピーを任意のネットワークに接続しない。 代わりに、物理的な安全な保管場所や商用ストレージ施設など、オフラインの場所に保存します。 障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを保存する必要があります。 バックアップ BLOB は、キー を完全に破棄するか、または操作不能Key Vaultキーマテリアルを復元する唯一の手段です。 Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。 顧客キーを使用した復元操作Key Vault Azure から取得したバックアップのみを使用できます。 したがって、キーをアップロードまたは作成した後に、Azure Key Vaultバックアップを作成する必要があります。
  
Azure キーのバックアップを作成Key Vault、[Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルで接尾辞を使用してください `.backup`。
  
このコマンドレットから生成される出力ファイルは暗号化され、Azure の外部で使用Key Vault。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。 これにより、ファイル名が自己記述的に作成されます。 また、バックアップ ファイル名が衝突しないことです。
  
例:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure の構成Key Vault検証する

DEP でキーを使用する前の検証はオプションですが、強くお勧めします。 この記事で説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証してください。
  
キーに 、および操作が `get`有効 `wrapKey`になっているか確認するには、次の `unwrapKey` 手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、アクセス ポリシーを探し、必要にExchange Online ID (GUID) または SharePoint オンライン ID (GUID) を探します。 上記の 3 つのアクセス許可はすべて[キーへのアクセス許可] の下に表示する必要があります。
  
アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、次のExchange OnlineとSkype for Business。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、[オンライン] と [SharePoint] のOneDrive for Business。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

キーに有効期限が設定されていないことを確認するには、 [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

顧客キーは有効期限が切れたキーを使用することはできません。 有効期限が切れたキーで試行された操作は失敗し、サービスが停止する可能性があります。 顧客キーで使用するキーには有効期限が設定されません。 有効期限を設定すると、削除できませんが、別の日付に変更できます。 有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。 有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365渡しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには、 [次のように Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーに有効期限を設定しません。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Azure の各キーの URI をKey Vaultする

キー コンテナーをセットアップしてキーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。 これらの URI は、後で各 DEP を作成して割り当てるときに使用します。したがって、この情報を安全な場所に保存します。 キー コンテナーごとにこのコマンドを 1 回実行します。
  
このAzure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>次の手順

この記事の手順を完了したら、DEP を作成して割り当てる準備ができました。 手順については、「顧客キーの [管理」を参照してください](customer-key-manage.md)。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)