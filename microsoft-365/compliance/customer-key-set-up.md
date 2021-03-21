---
title: アプリケーション レベルで顧客キーを設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーをセットアップする方法について説明します。
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922721"
---
# <a name="set-up-customer-key-at-the-application-level"></a>アプリケーション レベルで顧客キーを設定する

顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft 365 を構成して、Microsoft のデータ センターで保存されているデータを暗号化します。 つまり、顧客キーを使用すると、顧客は自分のキーを使用して、自分に属する暗号化の層を追加できます。 保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。

顧客キーを 365 に使用するには、Azure をOfficeがあります。 この記事では、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、365 でカスタマー キーを設定する手順Officeします。 Azure のセットアップが完了したら、組織内のメールボックスとファイルに割り当てるポリシー、つまりどのキーを割り当てるか決定します。 ポリシーを割り当てないメールボックスとファイルは、Microsoft によって制御および管理される暗号化ポリシーを使用します。 顧客キーの詳細、または一般的な概要については、「Service Encryption with Customer Key in customer Key in Office [365」を参照してください](customer-key-overview.md)。
  
> [!IMPORTANT]
> この記事のベスト プラクティスに従ってください。 これらは TIP および **IMPORTANT** として呼び **出されます**。 顧客キーを使用すると、組織全体と同じ規模のスコープを持つルート暗号化キーを制御できます。 つまり、これらのキーの間違いは大きな影響を与え、サービスの中断やデータの取り消しできない損失を引き起こす可能性があります。
  
## <a name="before-you-set-up-customer-key"></a>顧客キーを設定する前に

開始する前に、組織に適切なライセンスを持っている必要があります。 クラウド サービス プロバイダーまたはクラウド サービス プロバイダーを使用して、支払マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。 Pay As You Go プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。 2020 年 4 月 1 日より、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。 Office 365 Advanced Compliance SKU は、新しいライセンスの調達に使用できなくなりました。 既存のOffice 365 Advanced Compliance ライセンスは引き続きサポートされます。

この記事の概念と手順については [、Azure Key Vault のドキュメントを参照](/azure/key-vault/) してください。 また、Azure で使用される用語 (Azure テナントなど) [をADします](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。

FastTrack は、顧客キーの登録に使用される必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。 顧客キーオファーは FastTrack 経由で公開され、お客様とパートナーが同じ方法で必要な情報を提出する際に便利です。 FastTrack を使用すると、オファーで提供するデータを簡単にアーカイブできます。
  
ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティング サービス (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。 ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、および視点をユーザーに customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>顧客キーを設定する手順の概要

顧客キーを設定するには、これらのタスクを一覧表示された順序で実行します。 この記事の残りの部分では、各タスクの詳細な手順を説明するか、プロセスの各ステップの詳細情報にリンクします。
  
**Azure および Microsoft FastTrack では、次の情報を使用します。**
  
これらのほとんどのタスクは、Azure PowerShell にリモートで接続して完了します。 最適な結果を得る場合は、バージョン 4.4.0 以降の Azure PowerShell を使用します。
  
- [2 つの新しい Azure サブスクリプションを作成する](#create-two-new-azure-subscriptions)

- [必須の保持期間を使用するように Azure サブスクリプションを登録する](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  登録には 1 ~ 5 営業日かかる場合があります。

- [顧客キーをアクティブ化する要求を 365 Officeする](#submit-a-request-to-activate-customer-key-for-office-365)

2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている Web フォームを完了して、適切な顧客キー オファー要求を提出する必要があります。 **FastTrack チームは顧客キーのサポートを提供しない。Office FastTrack** ポータルを使用してフォームを送信し、顧客キーに関する関連するオファーを追跡するのに役立ちます。

- [各サブスクリプションにプレミアム Azure Key Vault を作成する](#create-a-premium-azure-key-vault-in-each-subscription)

- [各キー コンテナーにアクセス許可を割り当てる](#assign-permissions-to-each-key-vault)

- [キー コンテナーでソフト削除を有効にして確認する](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [キーを作成またはインポートして、各キー コンテナーにキーを追加する](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [キーの回復レベルを確認する](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault のバックアップ](#back-up-azure-key-vault)

- [Azure Key Vault 構成設定の検証](#validate-azure-key-vault-configuration-settings)

- [各 Azure Key Vault キーの URI を取得する](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365:**
  
Exchange Online と Skype for Business:
  
- [Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [メールボックスへの DEP の割り当て](#assign-a-dep-to-a-mailbox)

- [メールボックスの暗号化を検証する](#validate-mailbox-encryption)

SharePoint Online および OneDrive for Business:
  
- [SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online、OneDrive for Business、Teams ファイルのファイル暗号化を検証する](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する

Azure Key Vault でこれらのタスクを実行します。 Exchange Online および Skype for Business または SharePoint Online、OneDrive for Business、Teams ファイル、または Office 365 でサポートされているすべてのサービスに対してカスタマー キーを設定する場合は、これらの手順を実行する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

顧客キーには、2 つの Azure サブスクリプションが必要です。 ベスト プラクティスとして、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。 Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織で使用されるのと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。 たとえば、組織でグローバル管理者特権を持つ仕事用または学校用のアカウントを使用します。 詳細な手順については、「組織として [Azure にサインアップする」を参照してください](/azure/active-directory/fundamentals/sign-up-organization)。
  
> [!IMPORTANT]
> 顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。 これらの Azure サブスクリプションは、365 の暗号化キーを管理する場合にのみOffice必要があります。 これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織が保護されます。
>

組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。 これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>顧客キーをアクティブ化する要求を 365 Officeする

Azure の手順を完了したら、Microsoft FastTrack ポータルでオファー要求を送信 [する必要があります](https://fasttrack.microsoft.com/)。 FastTrack Web ポータルから要求を送信すると、Microsoft は、指定した Azure Key Vault 構成データと連絡先情報を確認します。 組織の承認された役員に関するオファー フォームで行う選択は重要であり、顧客キー登録の完了に必要です。 組織の役員は、顧客キーデータ暗号化ポリシーで使用されるすべてのキーを取り消して破棄する要求の信頼性を保証します。 この手順を 1 回実行して、Exchange Online および Skype for Business カバレッジのカスタマー キーをアクティブ化し、もう 1 回は SharePoint Online と OneDrive for Business のカスタマー キーをアクティブにする必要があります。
  
顧客キーをアクティブ化するオファーを送信するには、次の手順を実行します。
  
1. 組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Microsoft FastTrack ポータルにサインインします](https://fasttrack.microsoft.com/)。

2. ログインしたら、ダッシュボードを参照 **します**。

3. ナビゲーション **バーから [展開**] を選択するか **、[** 展開 **情報カード** のすべての展開リソースを表示する] を選択し、現在のオファーの一覧を確認します。

4. 該当するオファーの情報カードを選択します。

   - **Exchange Online と Skype for Business:** Exchange オンライン **オファーの暗号化キーの要求ヘルプを選択** します。

   - **SharePoint Online、OneDrive、Teams ファイル:** Sharepoint および **OneDrive オファーの暗号化キーの要求ヘルプを選択** します。

5. オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。

6. オファー フォームに該当する詳細情報と要求された情報を入力します。 暗号化キーとデータの永続的で不可逆的な破壊を承認するために承認する組織の役員の選択に特に注意を払います。 フォームが完成したら、[送信] を **選択します**。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>必須の保持期間を使用するように Azure サブスクリプションを登録する

ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。 このため、Customer Key で使用されるリソースには強力な保護が必要です。 Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。 必須の保持期間の Azure サブスクリプションにタグを付 *けまたは登録できます*。 必須の保持期間によって、Azure サブスクリプションの即時および取り消し不可の取り消しが防止されます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、Microsoft 365 チームとの共同作業が必要です。 このプロセスには、1 ~ 5 営業日かかる場合があります。 以前は、必須の保持期間を "キャンセルしない" と呼ばれる場合があります。
  
Microsoft 365 チームに連絡する前に、カスタマー キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。 開始する前に [、Azure PowerShell Az](/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。
  
1. Azure PowerShell でサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。

2. 必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスを完了するには、Microsoft にお問い合わせください。 SharePoint および OneDrive for Business チームの場合は、次の[spock@microsoft.com。](mailto:spock@microsoft.com) Exchange Online および Skype for Business の場合は、 [次の](mailto:exock@microsoft.com)exock@microsoft.com。 メールに次の情報を含める。

   **件名**: 顧客キー \<*Your tenant's fully qualified domain name*\>

   **本文**: 必須の保持期間を完了するサブスクリプションの Get-AzProviderFeatureを含める。

   このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。

4. 登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure Key Vault を作成する

キー コンテナーを作成する手順については、「Azure Key Vault の使用を開始する」に記載されています。このガイドでは [、Azure](/azure/key-vault/general/overview)PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。
  
キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。 Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護のために HSM を使用できます。 カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れ、プレミアム SKU のみを使用する必要があります。 どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。 詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。
  
> [!IMPORTANT]
> 実稼働データには Premium SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。
  
顧客キーを使用する Microsoft 365 サービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。 たとえば、Exchange Online と Skype for Business のみ、または SharePoint Online と OneDrive for Business の場合は、1 組のコンテナーのみを作成します。 Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、2 組のキー コンテナーを作成します。
  
コンテナーを関連付ける DEP の使用目的を反映するキー コンテナーの名前付け規則を使用します。 名前付け規則の推奨事項については、以下の「ベスト プラクティス」セクションを参照してください。
  
データ暗号化ポリシーごとに、ペアにされた個別のコンテナー セットを作成します。 Exchange Online では、ポリシーをメールボックスに割り当てるときに、データ暗号化ポリシーのスコープが選択されます。 メールボックスには 1 つのポリシーのみを割り当て、最大 50 のポリシーを作成できます。 SharePoint Online ポリシーの範囲には、地理的な場所または地理的な場所にある組織内のすべてのデータが含 _まれます_。

キー コンテナーの作成には Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (小さいですが) が必要で、有効にした場合は Key Vault ログも保存されたデータが生成されます。 ベスト プラクティスとして、Microsoft は個別の管理者を使用して各リソース グループを管理し、関連する顧客キー リソースを管理する一連の管理者に対応した管理を推奨します。
  
> [!IMPORTANT]
> 可用性を最大化するには、キー コンテナーが Microsoft 365 サービスに近い地域にある必要があります。 たとえば、Exchange Online 組織が北米にある場合は、キー コンテナーを北米に配置します。 Exchange Online 組織がヨーロッパにある場合は、キー コンテナーをヨーロッパに配置します。
> 
> キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用と範囲の省略形を含める (たとえば、コンテナーが北アメリカにある Contoso SharePoint サービスの場合、名前の可能なペアは Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 です。 コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。 2017 年 7 月現在、コンテナー名は変更できません。ベスト プラクティスは、セットアップの計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。
> 
> 可能であれば、ペア以外の領域にコンテナーを作成します。 ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。 したがって、地域のペアは、互いにバックアップ領域と見なされます。 つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。 このため、データ暗号化ポリシーで使用される 2 つのコンテナーに対してリージョンを選択すると、領域がペアになります。つまり、可用性の合計 2 つの領域だけが使用されます。 ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。 可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。 これは、可用性の合計 4 つの地域の恩恵を受ける。 詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。
  
### <a name="assign-permissions-to-each-key-vault"></a>各キー コンテナーにアクセス許可を割り当てる

実装に応じて、キー コンテナーごとに 3 つのアクセス許可セットを定義する必要があります。 たとえば、次のそれぞれに 1 つのアクセス許可セットを定義する必要があります。
  
- **組織のキー** コンテナーの毎日の管理を行うキー コンテナー管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。

  > [!IMPORTANT]
  > キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。 これは意図的で重要なプラクティスです。 暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。 ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。 代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。
  
  これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。

- 必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   次に例を示します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。 従業員がチームを離れるか、チームに参加する場合は、これらのアクセス許可を変更する必要があります。 キー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、アクセス許可を変更する必要があります。 この一連のキー コンテナー投稿者には、キー コンテナーの **共同作成者** ロールを付与する必要があります。 このロールは、Azure リソース マネージャーを使用して割り当てできます。 詳細な手順については、「Use Role-Based Access Control を使用して Azure サブスクリプション リソースへの [アクセスを管理する」を参照してください](/azure/active-directory/role-based-access-control-configure)。 サブスクリプションを作成する管理者は、暗黙的にこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。

- Exchange Online と Skype for Business で顧客キーを使用する場合は、Exchange Online および Skype for Business に代わってキー コンテナーを使用するアクセス許可を Microsoft 365 に付与する必要があります。 同様に、SharePoint Online および OneDrive for Business で顧客キーを使用する場合は、SharePoint Online および OneDrive for Business に代わってキー コンテナーを使用するアクセス許可を Microsoft 365 に追加する必要があります。 Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   ここで、

    - *コンテナー名* は、作成したキー コンテナーの名前です。

    - Exchange Online および Skype for Business の場合は、Office  *365 appID* を `00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online、OneDrive for Business、Teams ファイルの場合は  *、365 appID Officeに置き換* える `00000003-0000-0ff1-ce00-000000000000`

  例: Exchange Online と Skype for Business のアクセス許可の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  例: SharePoint Online、OneDrive for Business、Teams ファイルのアクセス許可を設定します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キー コンテナーでソフト削除を有効にして確認する

キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。 顧客キーでキーを使用するには、この構成 (Soft Delete と呼ばれる) を有効にする必要があります。 Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。
  
キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。
  
1. Azure サブスクリプションにサインインし、Windows PowerShell。 手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。

2. [Get-AzKeyVault コマンドレットを実行](/powershell/module/az.keyvault/get-azkeyvault)します。 この例では、 *コンテナー名* は、ソフト削除を有効にするキー コンテナーの名前です。

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** コマンドレットを実行して、キー コンテナーに対してソフト削除が構成されていることを確認します。 キー コンテナーに対してソフト削除が適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートして、各キー コンテナーにキーを追加する

Azure Key Vault にキーを追加するには、2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。 Key Vault で直接キーを作成する方法は複雑ではありません。一方で、キーをインポートすると、キーの生成方法を完全に制御できます。 RSA キーを使用します。 Azure Key Vault では、楕円曲線キーを使用した折り返しとラップ解除はサポートされていません。
  
キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

ここで、

- *コンテナー名* は、キーを作成するキー コンテナーの名前です。

- *キー名* は、新しいキーを指定する名前です。

  > [!TIP]
  > キー コンテナーの上記と同様の名前付け規則を使用してキーに名前を付ける。 この方法では、キー名のみを表示するツールでは、文字列は自己記述型です。
  
キーを HSM で保護する場合は、必ず **、Destination** パラメーターの値としてHSM を指定し、それ以外の場合は[ソフトウェア] を指定 **します**。

例えば、
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

キーをキー コンテナーに直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。
  
一部の組織では、キーの証明を確立するためにこのアプローチを好み、次の構成証明も提供します。
  
- インポートに使用されるツールセットには、生成するキーの暗号化に使用されるキー Exchange キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の HSM 内で生成される nCipher からの構成証明が含まれます。

- ツールセットには、nCipher によって製造された正規の HSM で Azure Key Vault セキュリティの世界も生成されたという nCipher からの構成証明が含まれています。 この構成証明は、Microsoft が本物の nCipher ハードウェアも使用しているという証明です。

セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。 オンプレミスでキーを作成し、キー コンテナーにインポートする詳細な手順については [、「Azure Key Vault](/azure/key-vault/keys/hsm-protected-keys)の HSM で保護されたキーを生成および転送する方法」を参照してください。 Azure の手順を使用して、各キー コンテナーにキーを作成します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。 サブスクリプションの設定を確認するには、キーの回復レベルを確認します。
  
キーの回復レベルを確認するには、Azure PowerShell で、次のように Get-AzKeyVaultKeyコマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、サブスクリプションを [キャンセルしない] リストに入れ、各キー コンテナーでソフト削除が有効になっていることを確認します。
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault のバックアップ

作成直後またはキーに対する変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。 オフライン コピーは、物理的な安全な保管場所や商用ストレージ施設など、ネットワークに接続できません。 障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを保存する必要があります。 バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。 Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 したがって、キーのアップロードまたは作成後に Azure Key Vault のバックアップを作成する必要があります。
  
Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルで接尾辞を使用してください `.backup` 。
  
このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。 これにより、ファイル名が自己記述的に作成されます。 また、バックアップ ファイル名が衝突しないことです。
  
次に例を示します。
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 構成設定の検証

DEP でキーを使用する前の検証はオプションですが、強くお勧めします。 この記事で説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に、Azure Key Vault リソースの正常性を検証してください。
  
キーに 、および操作 `get` が有効 `wrapKey` になっている `unwrapKey` か確認するには、次の手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、アクセス ポリシーと Exchange Online ID (GUID) または SharePoint Online ID (GUID) を必要に応じて探します。 上記の 3 つのアクセス許可はすべて[キーへのアクセス許可] の下に表示する必要があります。
  
アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、Exchange Online と Skype for Business の場合:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、SharePoint Online および OneDrive for Business の場合、
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

顧客キーは有効期限が切れたキーを使用することはできません。 有効期限が切れたキーで試行された操作は失敗し、サービスが停止する可能性があります。 顧客キーで使用するキーには有効期限が設定されていないことを強く推奨します。 有効期限を設定すると、削除できませんが、別の日付に変更できます。 有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。 有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーに有効期限を設定しません。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

キー コンテナーをセットアップしてキーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。 後で各 DEP を作成して割り当てる場合は、これらの URI を使用する必要があります。そのため、この情報を安全な場所に保存します。 キー コンテナーごとにこのコマンドを 1 回実行します。
  
Azure PowerShell では、次の情報を使用します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online と Skype for Business のカスタマー キーの設定

開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細 [については、「Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Exchange Online にリモートで接続して、次の手順をWindows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。 DEP を Microsoft 365 のメールボックスに割り当てる。 その後、Microsoft 365 はポリシーで識別されたキーを使用してメールボックスを暗号化します。 DEP を作成するには、前に取得した Key Vault URI が必要です。 手順 [については、「各 Azure Key Vault キーの URI を取得する」](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。
  
覚えておいてください! DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。
  
DEP を作成するには、次の手順を実行します。
  
1. ローカル コンピューターで、組織内のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、別のウィンドウで [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) にWindows PowerShellします。

2. DEP を作成するには、次のコマンドNew-DataEncryptionPolicyコマンドを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes。

   - *ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。 説明にスペースを含めることができます。 たとえば、「米国とその地域のメールボックスのルート キー」です。

   - *KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。 たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。 2 つの URI をコンマとスペースで区切ります。

   例:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

構文とパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスへの DEP の割り当て

DEP をメールボックスに割り当てるには、このコマンドレットSet-Mailboxします。 ポリシーを割り当てると、Microsoft 365 は DEP で識別されたキーを使用してメールボックスを暗号化できます。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailboxIdParameter はユーザー* メールボックスを指定します。 このコマンドレットの詳細についてはSet-Mailbox [Set-Mailbox を参照してください](/powershell/module/exchange/set-mailbox)。

ハイブリッド環境では、Exchange Online テナントに同期されているオンプレミスのメールボックス データに DEP を割り当てできます。 この同期されたメールボックス データに DEP を割り当てるには、次のコマンドレットSet-MailUserします。 ハイブリッド環境のメールボックス データの詳細については、「ハイブリッドモダン認証を使用した Outlook for iOS および Android を使用するオンプレミスメールボックス」 [を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailUserIdParameter はメール* ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。 このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化を検証する

メールボックスの暗号化には時間がかかる場合があります。 初めてのポリシー割り当てでは、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。 DEP を変更した後、または初めてメールボックスに DEP を割り当てると、暗号化の検証を試行するまで 72 時間待機することをお勧めします。
  
メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は true、メールボックスが暗号化されていない場合は **false** の値を返します。 メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数と、メールボックスのサイズによって異なります。 DEP を割り当てた時刻から 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーの設定

開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細 [については、「Azure Key Vault および Microsoft FastTrack for Customer Key のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーを設定するには、SharePoint Online にリモートで接続して、これらの手順をWindows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する

DEP を Azure Key Vault に格納されている一連のキーに関連付ける。 DEP は、地理と呼ばれる 1 つの地理的な場所のすべてのデータに適用します。 Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を使用して、地域ごとに 1 つの DEP を作成できます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、Teams ファイルで使用するために、組織内に 1 つの DEP を作成できます。 Microsoft 365 では、DEP で識別されたキーを使用して、その地域のデータを暗号化します。 DEP を作成するには、前に取得した Key Vault URI が必要です。 手順 [については、「各 Azure Key Vault キーの URI を取得する」](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。
  
覚えておいてください! DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。
  
DEP を作成するには、サーバーを使用して SharePoint Online にリモートWindows PowerShell。
  
1. ローカル コンピューターで、組織内でグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して [、SharePoint Online PowerShell に接続します](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)。

2. Microsoft SharePoint Online 管理シェルで、次のように Register-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   例:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   DEP を登録すると、geo のデータで暗号化が開始されます。 暗号化には時間がかかる場合があります。 このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。

### <a name="validate-file-encryption"></a>ファイルの暗号化を検証する

 SharePoint Online、OneDrive for Business、Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。 State _プロパティ_ は、顧客キーの暗号化が有効で、すべてのサイト内のすべてのファイルが暗号化されている場合に、登録済みの値を返します。 暗号化がまだ進行中の場合、このコマンドレットは登録の値を **返します**。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)