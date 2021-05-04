---
title: テナント レベルの Microsoft 365 の [カスタマー]キー (パブリック プレビュー)
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: テナント レベルでデータの顧客キーをMicrosoft 365する方法について学習します。
ms.openlocfilehash: 90ad08059d6b71583850368a70e32167b9defe88
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100796"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>テナント レベルでの顧客キー Microsoft 365の概要 (パブリック プレビュー)

指定したキーを使用して、データ暗号化ポリシー (DEP) を作成し、テナントに割り当てできます。 作成するテナント全体の DEP は、次のデータを暗号化します。

- Teamsチャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)
- Teamsメディア メッセージ (画像、コード スニペット、ビデオ メッセージ、オーディオ メッセージ、Wiki イメージ)
- Teamsストレージに保存されている通話と会議のTeams記録
- Teamsチャット通知
- Teams Cortana によるチャットの提案
- Teams状態メッセージ
- ユーザーとシグナルの情報をExchange Online
- Exchange Onlineレベルでまだ暗号化されていない顧客キー DEP のメールボックス
- MIP 完全データ一致 (EDM) データ – (データ ファイル スキーマ、ルール パッケージ、および機密データのハッシュに使用される塩)

Microsoft Information Protection および Microsoft Teams、テナント レベルの顧客キーは、DEP をテナントに割り当てる時点から新しいデータを暗号化します。 パブリック プレビューでは、過去のデータの暗号化はサポートされていません。 たとえばExchange Online、顧客キーは既存のデータと新しいデータを暗号化します。

テナントごとに複数の DEP を作成できますが、一度に割り当てできる DEP は 1 つのみです。 DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズに応じて完了に時間がかかっています。

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>テナント レベルのポリシーは、顧客キーに対するより広範な制御を追加Microsoft 365

顧客キーが Exchange Onlineおよび Sharepoint Online に対して既に設定されている場合は、新しいテナント レベルのパブリック プレビューがどのように適合しているかについて説明します。

作成するテナント レベルの暗号化ポリシーは、Microsoft TeamsワークロードとExchange Onlineのすべてのデータを暗号化Microsoft 365。 ただし、Exchange Online、顧客キー DEP を個々のメールボックスに既に割り当て済みの場合、テナント レベルのポリシーはそれらの DEP を上書きされません。 テナント レベルのポリシーは、メールボックス レベルの Customer Key DEP が既に割り当てられていないメールボックスのみを暗号化します。 テナント レベルの DEP を使用してユーザー メールボックスを暗号化すると、そのすべてのコンテンツが暗号化されます。 アプリケーション レベルで DEP で暗号化される情報については、「顧客キーを使用した [サービス暗号化」を参照してください](customer-key-overview.md)。

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a>テナント レベルの顧客キーで暗号化されていないデータ

顧客キーは、テナント レベルで次の種類のデータを暗号化します。 代わりに、Microsoft 365他の種類の暗号化を使用してこのデータを保護します。

- Exchangeレベルで Customer Key DEP を使用して暗号化済みのオンライン メールボックスを作成します。 顧客キー DEP が割り当てられていないメールボックスは、テナント レベルの DEP を使用して暗号化されます。 この配置は、一部のメールボックスがテナント レベルの DEP で暗号化され、一部のメールボックスがアプリケーション レベルの DEP で暗号化される可能性があります。
- SharePointおよびOneDrive for Businessアプリケーション レベルで顧客キーを使用します。 1 つの DEP は、1 つの地域SharePointコンテンツを暗号化します。
- Microsoft Teams および Teams および OneDrive for Business および SharePoint に保存された一部の通話および会議の記録は、SharePoint オンライン DEP によって暗号化されます。

顧客キーで現在サポートされていないワークロードまたはシナリオは、Microsoft 365。

- その他Microsoft 365ワークロード (Yammer、Planner など)。
- Teamsライブ イベントと Q&で A を選択します。 このTeamsシナリオは、テナント レベルで顧客キーによって暗号化されていない唯一のシナリオです。

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>テナント レベルで顧客キーを設定する (パブリック プレビュー)

これらの手順は類似していますが、アプリケーション レベルで顧客キーを設定する手順と同じではありません。 このパブリック プレビューは、テスト テナントのテスト データでのみ使用します。 このリリースは、実稼働データや実稼働環境では使用しない。 顧客キーの実稼働展開が既にある場合は、次の手順を使用して、テスト環境のテナント レベルで顧客キーを設定します。 テナント レベルの DEP をテナントに割り当てたら、検証プロセスを開始し、質問や懸念事項 m365ck@microsoft.com 問い合わせできます。 ドキュメントの検証手順については、「データ保存時の暗号化の検証手順」のパブリック[プレビュー](https://aka.ms/CustomerKey/PublicPreviewValidation)Microsoft 365。

これらのタスクのほとんどを完了するには、リモートでユーザーに接続Azure PowerShell。 最適な結果を得る場合は、バージョン 4.4.0 以降のバージョンを使用Azure PowerShell。

開始する前に:

- テナント レベルで顧客キーを設定するには、コンプライアンス管理者の役割を持つ仕事または学校のアカウントを使用する必要があります。
- 組織に適切なライセンスを持っている必要があります。 クラウド サービス プロバイダーまたはクラウド サービス プロバイダーを使用して、支払Enterprise Agreement Azure サブスクリプションを使用します。 Pay As You Go プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。 2020 年 4 月 1 日より、Office 365 のカスタマー キーは Office 365 E5、Microsoft 365 E5、Microsoft 365 E5 Compliance、Microsoft 365 E5 の情報保護 & SKU で提供されます。 Office 365 Advanced ComplianceSKU は、新しいライセンスでは使用できなくなりました。 既存のOffice 365 Advanced Complianceライセンスは引き続きサポートされます。 テナントの下で少なくとも 1 人の適切なライセンスを持つユーザーでサービスを有効にできますが、サービスの恩恵を受けるすべてのユーザーが適切なライセンスを持っている必要があります。

### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 2 つのキーを作成するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、組織の個別のメンバーが各サブスクリプションで 1 つのキーを構成する必要があります。 これらの Azure サブスクリプションのみを使用して、暗号化キーを管理Microsoft 365。 これらのガイドラインに従って、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、その他の方法で責任を負うキーを誤って管理したりした場合に、組織を保護するのに役立ちます。

組織に対して作成できる Azure サブスクリプションの数に実際的な制限はありません。 このベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えるのに役立ちます。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>必須の保持期間を使用するように Azure サブスクリプションを登録する

ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、壊滅的な操作を受け入れ、データが失われる可能性があります。 このため、Customer Key で使用されるリソースには強力な保護が必要です。 Customer Key で使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。 Azure サブスクリプションは、即時で取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。 このプロセスは、必須の保持期間の登録と呼ばれます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順では、Microsoft とのコラボレーションが必要です。 このプロセスには最大 5 営業日かかる場合があります。 以前は、このプロセスを "キャンセルしない" と呼ばれる場合があります。
  
チームに連絡するMicrosoft 365、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。 開始する前に、Azure PowerShell [Az](/powershell/azure/new-azureps-module-az)モジュールがインストールされていることを確認します。

1. サインインするには、Azure PowerShell。 手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)

2. 必須の保持Register-AzProviderFeature使用するサブスクリプションを登録するには、Register-AzProviderFeatureコマンドレットを実行します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Microsoft に問い合わせ、プロセスを完了[m365ck@microsoft.com。](mailto:m365ck@microsoft.com) メールに次のコンテンツを含める。

   **件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\>

   **本文**: 必須の保持期間を確定するサブスクリプションの ID。
   各サブスクリプションのGet-AzProviderFeature出力。

   このプロセスを完了するサービス レベル契約 (SLA) は、Microsoft がサブスクリプションを登録して必須の保持期間を使用すると通知 (および確認) された後、5 営業日です。

4. 登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 確認された場合、Get-AzProviderFeatureコマンドは、Registration State プロパティの **[登録済** み] **の値を返** します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure Key Vault を作成する

キー コンテナーを作成する手順については[、「Azure Key Vault](/azure/key-vault/general/overview)の使用を開始する」に記載されています。このガイドでは、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループ内のキー コンテナーの作成について説明します。
  
キー コンテナーを作成する場合は、SKU (標準または標準) を選択プレミアム。 標準 SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます 。ハードウェア セキュリティ モジュール (HSM) キー保護はありません)、プレミアム SKU では、キー コンテナー キーの保護のために HSM を使用できます。 顧客キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、MICROSOFT では、SKU の一部のみを使用プレミアム強く推奨しています。 どちらの種類のキーを使用する操作のコストも同じなので、コストの唯一の違いは、各 HSM で保護されたキーの 1 か月あたりのコストです。 詳細については [、「Key Vault の価格」](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。
  
> [!IMPORTANT]
> 実稼働データプレミアム SKU キー コンテナーと HSM で保護されたキーを使用し、テストおよび検証の目的で標準 SKU キー コンテナーとキーのみを使用します。

キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める。 たとえば、コンテナーが北アメリカにある Contoso サービスの場合、名前の可能なペアは Contoso-O365-NA-VaultA1 と Contoso-O365-NA-VaultA2 です。 コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が既に他の Azure ユーザーによって要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。 構成が完了すると、コンテナー名を変更できないので、ベスト プラクティスは、セットアップ用の計画を作成し、2 人目を使用して計画が正しく実行されていることを確認する方法です。

可能であれば、ペア以外の領域にコンテナーを作成します。 ペアリングされた Azure リージョンは、サービス障害ドメイン全体で高可用性を提供します。 したがって、地域のペアは、互いにバックアップ領域と見なされます。 1 つの地域に配置される Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得しています。 データ暗号化ポリシーで使用される 2 つのコンテナーのリージョンを選択すると、リージョンがペアになります。つまり、使用できる領域は合計 2 つのみです。 ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。 可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアリングされていない 2 つの領域を選択します。 このシナリオでは、可用性の合計 4 つの地域の恩恵を受ける。 詳細については [、「Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for current list of region pairs」を参照してください。

### <a name="assign-permissions-to-each-key-vault"></a>各キー コンテナーにアクセス許可を割り当てる

キー コンテナーごとに、実装に応じて、顧客キーに対して 3 つの個別のアクセス許可セットを定義する必要があります。 たとえば、次に示す各アクセス許可のセットを 1 つ定義する必要があります。
  
- **組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。

  > [!IMPORTANT]
  > キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。 これは意図的で重要なプラクティスです。 暗号化キーを削除すると、データが完全に破棄されるので、通常は実行しません。 ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与しない。 代わりに、これを重要なコンテナーの投稿者に予約し、結果の明確な理解が得られると、短期間で管理者に割り当てる必要があります。
  
  これらのアクセス許可を組織内のユーザーに割り当てるには、Azure サブスクリプションにサインインし、Azure PowerShell。 手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)

   必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、このコマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   次に例を示します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure **Key Vault 自体の** アクセス許可を変更できるキー コンテナーの投稿者。 従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、これらのアクセス許可を変更する必要があります。 この一連のキー コンテナー投稿者には、キー コンテナーの共同作成者ロールを付与する必要があります。 このロールは、Azure リソース マネージャーを使用して割り当てできます。 詳細な手順については [、「Use Role-Based アクセス制御を使用](/azure/active-directory/role-based-access-control-configure) して Azure サブスクリプション リソースへのアクセスを管理する」を参照してください。 サブスクリプションを作成する管理者は、既定でこのアクセス権を持ち、他の管理者を共同作成者ロールに割り当てる機能を持っています。

- **Microsoft 365の作業を** テナント レベルで実行する保存時のデータ暗号化サービスを提供します。 アクセス許可を付与するにはMicrosoft 365構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  ここで、

  - *コンテナー名* は、作成したキー コンテナーの名前です。

  例: Rest Encryption サービスMicrosoft 365データの場合は、appID Microsoft 365 *に置き換* える`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キー コンテナーでソフト削除を有効にして確認する

キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因で、サービスの停止が長く発生する可能性が低い。 顧客キーでキーを使用する前に、Soft Delete と呼ばれるこの構成を有効にします。 Soft Delete を有効にすると、削除から 90 日以内にキーまたはコンテナーをバックアップから復元せずに復元できます。
  
キー コンテナーで Soft Delete を有効にするには、次の手順を実行します。
  
1. Azure サブスクリプションにサインインするには、Windows PowerShell。 手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)

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

### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除が有効になっている必要があります。 これらの設定を確認するには、キーの回復レベルを確認します。
  
キーの回復レベルを確認するには、次Azure PowerShell、Get-AzKeyVaultKeyコマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Recovery _Level_ プロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションをキャンセルしないリストに入れる手順のすべてと、各キー コンテナーで "soft delete" を有効にしたことを確認する必要があります。 次に、電子メールの出力のスクリーンショット `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` を電子メールに送信 m365ck@microsoft.com。

### <a name="back-up-azure-key-vault"></a>Azure Key Vault のバックアップ

作成直後、またはキーに対する変更の直後に、キーをバックアップし、バックアップのコピーをオンラインとオフラインの両方で保存します。 オフライン コピーを任意のネットワークに接続しない。 代わりに、物理的な安全または商用のストレージ施設に格納します。 障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。 バックアップ BLOB は、Key Vault キーを完全に破棄するか、操作不能にレンダリングする場合にキー マテリアルを復元する唯一の手段です。 Azure Key Vault の外部であり、Azure Key Vault にインポートされたキーは、顧客キーがキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 したがって、キーがアップロードまたは作成された後に Azure Key Vault のバックアップを作成する必要があります。
  
Azure Key Vault キーのバックアップを作成するには [、Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを次のように実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルで接尾辞を使用してください `.backup` 。
  
このコマンドレットから生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
次に例を示します。
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 構成設定の検証

DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。 特に、このトピックで説明する以外のキーとコンテナーをセットアップする手順を使用する場合は、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。
  
キーに get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、アクセス ポリシーを探し、必要にMicrosoft 365アプリ ID (GUID) を探します。 get、wrapKey、unwrapKey の 3 つの操作はすべて、[キーへのアクセス許可] の下に表示する必要があります。
  
アクセス ポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicyコマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

例: Rest Encryption サービスMicrosoft 365データの場合は、appID Microsoft 365 *に置き換* える`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

キーに有効期限が設定されていないことを確認するには [、Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

期限切れのキーは顧客キーでは使用できません。また、期限切れのキーで試行された操作は失敗し、サービスが停止する可能性があります。 顧客キーで使用するキーには有効期限が設定されていないことを強く推奨します。 有効期限を設定すると、削除できませんが、別の日付に変更できます。 有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。 有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365渡しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには、次のように [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。 後で各 DEP を作成して割り当てる場合は、これらの URI を使用する必要があります。そのため、この情報を安全な場所に保存します。 キー コンテナーごとにこのコマンドを 1 回実行してください。
  
次のAzure PowerShell。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>テナントの顧客キー暗号化ポリシーを設定する

これらのコマンドレットを実行するには、アクセス許可を割り当てる必要があります。 この記事ではコマンドレットのすべてのパラメーターを一覧表示しますが、割り当てられたアクセス許可にパラメーターが含まれていない場合は、一部のパラメーターにアクセスできない場合があります。 コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)」を参照してください。

### <a name="create-policy"></a>ポリシーの作成

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

説明: コンプライアンス管理者を有効にして、2 つの AKV ルート キーを使用して新しいデータ暗号化ポリシー (DEP) を作成します。 作成したポリシーは、このコマンドレットを使用してSet-M365DataAtRestEncryptionPolicyAssignmentできます。 キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。 新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。

例:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

パラメータ :

| 名前 | 説明 | オプション (Y/N) |
|----------|----------|---------|
|名前|データ暗号化ポリシーの表示名|×|
|AzureKeyIDs|データ暗号化ポリシーに関連付ける Azure Key Vault キーの 2 つの URI 値をコンマで区切って指定します。|×|
|説明|データ暗号化ポリシーの説明|×|

### <a name="assign-policy"></a>ポリシーの割り当て

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

説明: このコマンドレットは、既定のデータ暗号化ポリシーの構成に使用されます。 このポリシーは、すべてのサポート ワークロードでデータを暗号化するために使用されます。

例:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

パラメータ :

| 名前 | 説明 | オプション (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|割り当てる必要があるデータ暗号化ポリシーを指定します。ポリシー名またはポリシー ID を指定します。|×|

### <a name="modify-or-refresh-policy"></a>ポリシーの変更または更新

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

説明: コマンドレットを使用して、既存のポリシーを変更または更新できます。 また、ポリシーを有効または無効にするためにも使用できます。 キーを最初に割り当て、またはキーを回転した後、新しいキーを有効にするには最大 24 時間かかる場合があります。 新しい DEP の有効時間が 24 時間を超える場合は、Microsoft にお問い合わせください。

例:

データ暗号化ポリシーを無効にします。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

データ暗号化ポリシーを更新します。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

パラメータ :

| 名前 | 説明 | オプション (Y/N) |
|----------|----------|---------|
|-Identity|変更するデータ暗号化ポリシーを指定します。|×|
|-Refresh|Azure Key Vault で関連付けられたキーを回転した後、更新スイッチを使用してデータ暗号化ポリシーを更新します。 このスイッチで値を指定する必要はありません。|Y|
|-Enabled|Enabled パラメーターは、データ暗号化ポリシーを有効または無効にします。 ポリシーを無効にする前に、テナントからの割り当てを解除する必要があります。 有効な値は次のとおりです。</br > $true: ポリシーが有効になっている</br > $true: ポリシーを有効にします。これが既定値です。|Y|
|-Name|Name パラメーターは、データの暗号化ポリシーの一意の名前を指定します。|Y|
|-Description|Description パラメーターは、データの暗号化ポリシーの省略可能な説明を指定します。|Y|

### <a name="get-policy-details"></a>ポリシーの詳細を取得する

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

説明: このコマンドレットは、テナント用に作成された M365DataAtRest 暗号化ポリシーのすべて、または特定のポリシーに関する詳細を一覧表示します。

例:

この例では、組織内の M365DatAtRest 暗号化ポリシーの概要リストを返します。

```powershell
Get-M365DataAtRestEncryptionPolicy
```

この例では、"NAM Policy" という名前のデータ暗号化ポリシーの詳細情報を返します。

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

パラメータ :

| 名前 | 説明 | オプション (Y/N) |
|----------|----------|---------|
|-Identity|詳細を一覧表示するデータ暗号化ポリシーを指定します。|Y|

### <a name="get-policy-assignment-info"></a>ポリシーの割り当て情報を取得する

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

説明: このコマンドレットには、現在テナントに割り当てられているポリシーが一覧表示されます。

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a>テナント レベルでの顧客キーからのオフボーディング

Microsoft で管理されているキーに戻す必要がある場合は、可能です。 オフボードの場合、データは、個々のワークロードでサポートされる既定の暗号化を使用して再暗号化されます。 たとえば、Microsoft Exchange Onlineキーを使用した既定の暗号化がサポートされている場合です。

テナント レベルで顧客キーからテナントをオフボードする場合は、m365ck@microsoft.com[](mailto:m365ck@microsoft.com)サービスを "無効にする" 要求をメールで送信します。

> [!IMPORTANT]
> オフボードは、データ削除と同じではありません。 データの削除は、組織のデータを完全に暗号化削除し、Microsoft 365オフボードから削除します。 テナント レベルのポリシーに対してデータ削除を実行できません。 データ削除パスの詳細については、「キーを取り消して、データ削除パス [プロセスを開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

## <a name="about-the-availability-key"></a>可用性キーについて

可用性キーの詳細については、「可用性キーについて [」を参照してください](customer-key-availability-key-understand.md)。

## <a name="key-rotation"></a>キーの回転

顧客キーで使用するキーの回転またはローリングの詳細については、「顧客キーまたは可用性キーのロールまたはローテーション」 [を参照してください](customer-key-availability-key-roll.md)。 DEP を更新して新しいバージョンのキーを使用する場合は、この記事で前述したように、Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)
