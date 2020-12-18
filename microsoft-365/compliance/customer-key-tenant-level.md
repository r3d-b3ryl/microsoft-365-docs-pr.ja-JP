---
title: テナント レベルでの Microsoft 365 のカスタマー キー (パブリック プレビュー)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
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
description: Microsoft 365 テナント内のすべてのデータに対して顧客キーを設定する方法について説明します。
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712529"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>テナント レベルでの Microsoft 365 のカスタマー キーの概要 (パブリック プレビュー)

入力したキーを使用して、データ暗号化ポリシー (DEP) を作成し、それをテナントに割り当てできます。 DEP は、次のワークロードのデータをテナント全体で暗号化します。

- Teams のチャット メッセージ (1 対 1 のチャット、グループ チャット、会議チャット、チャネル会話)
- Teams のメディア メッセージ (画像、コード スニペット、ビデオ、Wiki 画像)
- Teams ストレージに保存された Teams の通話と会議のレコーディング
- Teams のチャット通知
- Cortana による Teams チャットの提案
- Teams のステータス メッセージ
- Exchange Online のユーザー情報とシグナル情報

Microsoft Teams の場合、テナント レベルの顧客キーは、DEP がテナントに割り当てられた時点からの新しいデータを暗号化します。 パブリック プレビューでは、過去のデータの暗号化はサポートされていません。 Exchange Online の場合、顧客キーは既存のデータと新しいデータのすべて暗号化を行います。

テナントごとに複数の DEP を作成できますが、任意の時点で割り当て可能な DEP は 1 つのみです。 DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズによっては完了に時間がかかる場合があります。

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>テナント レベルのポリシーにより、Microsoft 365 の顧客キーに対するより広範な制御が追加されます。

Exchange Online と Sharepoint Online のカスタマー キーが既に設定されている場合は、新しいテナント レベルのパブリック プレビューがどのように適合しているかについて説明します。

作成するテナント レベルの暗号化ポリシーは、Microsoft 365 の Microsoft Teams ワークロードと Exchange Online ワークロードのすべてのデータを暗号化します。 このポリシーは、顧客キーで既に作成した微調整された DEP に干渉しません。

例:

Microsoft Teams ファイルと、OneDrive for Business および SharePoint に保存されている一部の Teams 通話と会議のレコーディングは、SharePoint Online DEP によって暗号化されます。 1 つの SharePoint Online DEP が単一の geo 内のコンテンツを暗号化します。 テナント レベルの DEP は、暗号化されたデータを新しいポリシーで再び暗号化します。

Exchange Online では、顧客キーを使用して 1 つ以上のユーザー メールボックスを暗号化する DEP を作成できます。 テナント レベルのポリシーを作成する場合、そのポリシーは暗号化されたメールボックスを暗号化しなされません。 ただし、テナント レベルのキーは、DEP の影響を受けしていないメールボックスを暗号化します。

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>テナント レベルで顧客キーを設定する (パブリック プレビュー)

これらの手順は、アプリケーション レベルで顧客キーを設定する手順と似ていますが、同じではありません。 このパブリック プレビューは、テスト テナントのテスト データでのみ使用してください。 このリリースは、実稼働データと一緒に使用したり、実稼働環境で使用したりすることはできません。 顧客キーの実稼働展開が既にある場合は、次の手順を使用して、テスト環境のテナント レベルで顧客キーを設定します。

これらのタスクの大部分は、Azure PowerShell にリモートで接続することで完了します。 最善の結果を得る場合は、Azure PowerShell のバージョン 4.4.0 以降を使用してください。

開始する前に、次の情報を確認してください。

- テナント レベルで顧客キーを設定するには、コンプライアンス管理者の役割を持つ、仕事または学校のアカウントを使用する必要があります。
- 組織に適したライセンスを持っている必要があります。 サブスクリプションまたはクラウド サービス プロバイダーを使用して、有料マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。 [お支払い方法] プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。 2020 年 4 月 1 日から、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。 Office 365 Advanced Compliance SKU は、新しいライセンスの調達には使用できなくなりました。 既存の Office 365 Advanced Compliance ライセンスは引き続きサポートされます。 適切なライセンスを持つテナントの下で少なくとも 1 つのライセンスでサービスを有効にできる一方で、サービスの恩恵を受けるすべてのユーザーが適切なライセンスを持つことを確認する必要があります。 次のいずれかのライセンスが必要です。

### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、組織の個別のメンバーがサブスクリプションごとに 1 つのキーを構成する方法をお勧めします。 これらの Azure サブスクリプションのみを使用して、Microsoft 365 の暗号化キーを管理します。 これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織を保護します。

組織で作成できる Azure サブスクリプションの数に実際的な制限はありません。 このベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えるのに役立ちます。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure サブスクリプションを登録して必須の保持期間を使用する

ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、致命的な障害が発生したり、データが失われる可能性があります。 このため、顧客キーで使用されるリソースには強力な保護が必要です。 顧客キーと一緒に使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。 Azure サブスクリプションは、すぐに取り消し可能な取り消しを防ぐ方法でタグ付けまたは登録できます。 これは、必須の保持期間の登録と呼ばれます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順には、Microsoft とのコラボレーションが必要です。 このプロセスには、最大 5 営業日かかる場合があります。 以前は、これは "キャンセルしない" と呼ばれる場合があります。
  
Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。 開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。

1. Azure PowerShell でサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. Register-AzProviderFeatureコマンドレットを実行して、必須の保持期間を使用するためにサブスクリプションを登録します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスを完了するには、Microsoft にお問い [合](mailto:m365ck@microsoft.com)m365ck@microsoft.com。 メールに次の情報を含める:

   **件名**: 顧客キー \<*Your tenant's fully-qualified domain name*\>

   **Body**: 必須の保持期間を確定するサブスクリプションの ID です。
   各サブスクリプションのGet-AzProviderFeature出力。

   このプロセスを完了するサービス レベル 契約 (SLA) は、サブスクリプションを登録して必須の保持期間を使用したと Microsoft に通知 (および検証) が完了した 5 営業日後です。

4. 登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 確認された場合、Get-AzProviderFeatureコマンドは Registration State プロパティの **Registered** の値 **を返** します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. このプロセスを完了するには、次のコマンドRegister-AzResourceProviderします。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure Key Vault を作成する

キー コンテナーを作成する手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の使用を開始する」に記載されています。この手順では、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループでのキー コンテナーの作成について説明します。
  
キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。 Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます。ハードウェア セキュリティ モジュール (HS) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護に HSM を使用できます。 カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、Premium SKU のみを使用する方法を強く推奨している。 どちらの種類のキーも操作のコストは同じなので、コストの唯一の違いは、各HSM で保護されたキーの 1 か月あたりのコストです。 詳細 [については、Key Vault の価格を](https://azure.microsoft.com/pricing/details/key-vault/) 参照してください。
  
> [!IMPORTANT]
> 実稼働データには Premium SKU キー コンテナーと SKU で保護されたキーを使用し、テストと検証の目的には Standard SKU キー コンテナーとキーのみを使用します。

キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める。 たとえば、コンテナーが北米に位置する Contoso サービスの場合、名前のペアとして Contoso-O365-NA-VaultA1 と Contoso-O365-NA-VaultA2 を指定できます。 コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が他の Azure ユーザーによって既に要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。 構成したコンテナー名は変更できないので、ベスト プラクティスは、セットアップの計画を作成し、2 番目のユーザーを使用して計画が正しく実行されていることを確認する方法です。

可能であれば、ペアでない地域にコンテナーを作成します。 ペアの Azure リージョンは、サービス 障害ドメイン間で高可用性を提供します。 したがって、地域のペアは互いにバックアップ地域と考え合う可能性があります。 つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。 このため、地域がペアのデータ暗号化ポリシーで使用される 2 つのコンテナーに対して地域を選択すると、合計で 2 つの可用性の地域だけが使用されます。 ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。 可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアではない 2 つの地域を選択します。 これにより、合計で 4 つの可用性の領域を利用できます。 詳細については、「ビジネス継続性と障害復旧 [(BCDR): 地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) ペアの現在の一覧については、Azure のペアリングされた地域」を参照してください。

### <a name="assign-permissions-to-each-key-vault"></a>各キー コンテナーにアクセス許可を割り当てる

キー コンテナーごとに、実装に応じて、顧客キーに対する 3 つの個別のアクセス許可セットを定義する必要があります。 たとえば、次のそれぞれに対して 1 つのアクセス許可セットを定義する必要があります。
  
- **組織のキー** コンテナーの毎日の管理を実行するキー コンテナー管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、および復元が含まれます。

  > [!IMPORTANT]
  > キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。 これは意図的で重要な方法です。 暗号化キーを削除すると、データが完全に破棄されるので、通常は削除しません。 ベスト プラクティスとして、この権限をキー コンテナー管理者に既定で付与することはお使いください。 代わりに、主要なコンテナーの投稿者のためにこれを予約し、結果の明確な理解が得られると、短期的に管理者に割り当てる必要があります。
  
  組織内のユーザーにこれらのアクセス許可を割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにログインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

   必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、次のコマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   例:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure **Key Vault 自体** のアクセス許可を変更できる主要なコンテナーの投稿者。 従業員がチームを離れる、またはチームに参加する場合、またはキー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、これらのアクセス許可を変更する必要があります。 この一連の主要なコンテナー投稿者には、キー コンテナーの共同作成者ロールが付与されている必要があります。 このロールは、Azure リソース マネージャーを使用して割り当てできます。 詳細な手順については、「Role-Based [Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) を使用して Azure サブスクリプション リソースへのアクセスを管理する」を参照してください。 サブスクリプションを作成する管理者は、既定でこのアクセス権を持ち、他の管理者を投稿者の役割に割り当てる機能を持っています。

- テナント レベルで顧客キーの処理を行う、保存中の **Microsoft 365** データ暗号化サービス。 Microsoft 365 へのアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  ここで、

  - *コンテナー名* は、作成したキー コンテナーの名前です。

  例: Rest Encryption サービスの Microsoft 365 データの場合  *、Microsoft 365 appID* を次の値に置き換える `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キー コンテナーで回復可能な削除を有効にして確認する

キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因でサービスの停止が延長される可能性は低い可能性があります。 顧客キーでキーを使用する前に、この構成 (回復可能な削除と呼ばれる) を有効にします。 回復可能な削除を有効にすると、削除から 90 日以内にキーまたはコンテナーを復元できます。バックアップから復元する必要はありません。
  
キー コンテナーで回復可能な削除を有効にするには、次の手順を実行します。
  
1. Azure サブスクリプションにサインインするには、次のWindows PowerShell。 手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. [Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。 この例では、 *コンテナー名* は、回復可能な削除を有効にするキー コンテナーの名前です。

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** コマンドレットを実行して、キー コンテナーの回復可能な削除が構成されていることを確認します。 回復可能な削除がキー コンテナーに対して適切に構成されている場合 _、Soft Delete Enabled_ プロパティは True の値を返 **します**。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートして、各キー コンテナーにキーを追加する

Azure Key Vault にキーを追加するには 2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。 キーコンテナーで直接キーを作成する方法は複雑では少なく、キーをインポートすると、キーの生成方法を完全に制御できます。 RSA キーを使用します。 Azure Key Vault では、楕円曲線キーでの折り返しと折り返しの解除はサポートされていません。
  
キー コンテナーにキーを直接作成するには、次のように [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) コマンドレットを実行します。
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

ここで、

- *コンテナー名* は、キーを作成するキー コンテナーの名前です。

- *キー名* は、新しいキーを指定する名前です。

  > [!TIP]
  > キー コンテナーの場合は、上記と同様の名前付け規則を使用してキーに名前を付ける。 これにより、キー名のみを表示するツールでは、文字列は自己記述型になります。
  
キーを必ず _DESTINATION_ パラメーターの値として指定し、**それ** 以外の場合は **Software** を指定します。

例えば、
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除 (回復可能) が有効になっている必要があります。 これを確認するには、キーの回復レベルを確認します。
  
キーの回復レベルを確認するには、Azure PowerShell で次Get-AzKeyVaultKeyコマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

回復レベルのプロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、この記事を確認し、サブスクリプションを取り消し不可リストに入れるすべての手順を実行し、各キー コンテナーで "回復可能な削除" を有効にした必要があります。 次に、電子メールの出力のスクリーンショット `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` を送信して、m365ck@microsoft.com。

### <a name="back-up-azure-key-vault"></a>Azure Key Vault をバックアップする

キーの作成または変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。 オフライン コピーをネットワークに接続しない。 代わりに、物理的な安全なストレージまたは商用のストレージ機能に保存します。 障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。 バックアップ BLOB は、Key Vault キーが完全に破棄された場合や、他の方法で操作できない場合にキー マテリアルを復元する唯一の手段です。 Azure Key Vault の外部に存在し、Azure Key Vault にインポートされたキーは、顧客キーでキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 したがって、キーをアップロードまたは作成したら、Azure Key Vault のバックアップを作成する必要があります。
  
Azure Key Vault キーのバックアップを作成するには、 [次のように Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルでサフィックスが使用されている必要があります `.backup` 。
  
このコマンドレットによって生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
例:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault の構成設定を検証する

DEP でキーを使用する前に検証を実行する方法はオプションですが、強くお勧めします。 特に、このトピックで説明する手順以外の手順でキーとコンテナーをセットアップする場合は、顧客キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。
  
キーで get、wrapKey、および unwrapKey 操作が有効になっているか確認するには、次の手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、アクセス ポリシーと、必要に応じて Microsoft 365 アプリ ID (GUID) を探します。 Get、wrapKey、unwrapKey の 3 つの操作はすべて、[キーへのアクセス許可] の下に表示する必要があります。
  
アクセス ポリシーの構成が正しくない場合は、次Set-AzKeyVaultAccessPolicyコマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

例: Rest Encryption サービスの Microsoft 365 データの場合  *、Microsoft 365 appID* を次の値に置き換える `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

キーに有効期限が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

期限切れのキーを顧客キーで使用することはできません。また、期限切れのキーを使用して試行された操作は失敗し、サービスが停止する可能性があります。 顧客キーで使用するキーには有効期限日を設定することを強く推奨します。 有効期限を設定すると削除できませんが、別の日付に変更できます。 有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 9999 年 12 月 31 日に変更します。 有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには [、Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

Azure のすべての手順を完了してキー コンテナーをセットアップし、キーを追加したら、次のコマンドを実行して各キー コンテナーのキーの URI を取得します。 これらの URI は、後で各 DEP を作成して割り当てる際に使用する必要があります。そのため、この情報は安全な場所に保存してください。 このコマンドは、キー コンテナーごとに 1 回だけ実行してください。
  
Azure PowerShell の場合:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>テナントの顧客キーの暗号化ポリシーを設定する

これらのコマンドレットを実行する前に、アクセス許可を割り当てる必要があります。 この記事ではコマンドレットのすべてのパラメーターの一覧を示しますが、割り当てられたアクセス許可にパラメーターが含まれていない場合は、一部のパラメーターにアクセスできない場合があります。 コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)」を参照してください。

### <a name="create-policy"></a>ポリシーの作成

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

説明: コンプライアンス管理者が 2 つの AROOT ルート キーを使用して新しいデータ暗号化ポリシー (DEP) を作成できます。 作成されたポリシーは、このコマンドレットを使用Set-M365DataAtRestEncryptionPolicyできます。 キーを最初に割り当て、またはキーを回転した後に、新しいキーが有効にな最大 24 時間かかる場合があります。 新しい DEP が有効にするのに 24 時間以上かかる場合は、Microsoft にお問い合わせください。

例:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

パラメータ :

| Name | 説明 | 省略可能 (Y/N) |
|--|--|--|
|Name|データ暗号化ポリシーの表示名|×|
|AzureKeyIDs|データ暗号化ポリシーに関連付ける Azure Key Vault キーの 2 つの URI 値をコンマで区切って指定します。|×|
|説明|データ暗号化ポリシーの説明|×|

### <a name="assign-policy"></a>ポリシーの割り当て

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

説明 : このコマンドレットは、既定のデータ暗号化ポリシーの構成に使用されます。 このポリシーは、すべてのサポート ワークロードでデータを暗号化するために使用されます。 

例:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

パラメータ :
| Name | 説明 | 省略可能 (Y/N) |
|--|--|--|
-Policy|割り当てる必要があるデータ暗号化ポリシーを指定します。ポリシー名またはポリシー ID を指定します。|×|

### <a name="modify-or-refresh-policy"></a>ポリシーの変更または更新

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

説明 : このコマンドレットを使用して、既存のポリシーを変更または更新できます。 また、ポリシーを有効または無効にする場合にも使用できます。 キーを最初に割り当て、またはキーを回転した後に、新しいキーが有効にな最大 24 時間かかる場合があります。 新しい DEP が有効にするのに 24 時間以上かかる場合は、Microsoft にお問い合わせください。

例:

データ暗号化ポリシーを無効にします。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

データ暗号化ポリシーを更新します。

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

パラメータ :
| Name | 説明 | 省略可能 (Y/N) |
|--|--|--|
|-Identity|変更するデータ暗号化ポリシーを指定します。|×|
|-Refresh|Azure Key Vault で関連付けられたキーを回転した後、Refresh スイッチを使用してデータ暗号化ポリシーを更新します。 このスイッチで値を指定する必要はありません。|Y|
|-Enabled|Enabled パラメーターは、データ暗号化ポリシーを有効または無効にします。 ポリシーを無効にする前に、テナントからポリシーの割り当てを解除する必要があります。 有効な値は次のとおりです。</br > $true: ポリシーが有効になっている</br > $true: ポリシーを有効にします。これが既定値です。|Y|
|-Name|Name パラメーターは、データの暗号化ポリシーの一意の名前を指定します。|Y
|-Description|Description パラメーターは、データの暗号化ポリシーの省略可能な説明を指定します。|Y|

### <a name="get-policy-details"></a>ポリシーの詳細を取得する

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

説明 : このコマンドレットは、テナント用に作成された M365DataAtRest 暗号化ポリシーの一覧、または特定のポリシーに関する詳細を一覧表示します。

例:

この例では、組織内の M365DatAtRest Encryption ポリシーの要約リストを返します。

```powershell
Get-M365DataAtRestEncryptionPolicy
```

この例では、"NAM Policy" という名前のデータ暗号化ポリシーの詳細情報を返します。

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

パラメータ :

| Name | 説明 | 省略可能 (Y/N) |
|--|--|--|
|-Identity|詳細を一覧表示するデータ暗号化ポリシーを指定します。|Y|

### <a name="get-policy-assignment-info"></a>ポリシー割り当て情報を取得する

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

説明 : このコマンドレットは、テナントに現在割り当てられているポリシーを一覧表示します。

## <a name="offboarding-from-customer-key"></a>顧客キーからのオフボード

Microsoft で管理されているキーに戻す必要がある場合は、次の操作を行います。 オフボードすると、個々のワークロードでサポートされている既定の暗号化を使用してデータが再暗号化されます。 たとえば、Exchange Online は、Microsoft が管理するキーを使用した既定の暗号化をサポートしています。

テナント レベルで顧客キーからテナントをオフボードすることを決定した場合は、m365ck@microsoft.com でテナントのサービスを "無効にする" 要求を電子メールで Microsoft [に連絡します](mailto:m365ck@microsoft.com)。

> [!IMPORTANT]
> オフボードは、データ消去と同じではありません。 データの削除は、Microsoft 365 から組織のデータを完全に暗号化して削除しますが、オフボードは削除を行う必要があります。 テナント レベルのポリシーのデータ消去は実行できません。 データ削除パスの詳細については、「キーを取り消す」を [参照し、データ消去パスプロセスを開始します](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

## <a name="about-the-availability-key"></a>可用性キーについて

可用性キーの詳細については、「可用性キー [の詳細」を参照してください](customer-key-availability-key-understand.md)。

## <a name="key-rotation"></a>キーの回転

顧客キーで使用されるキーの回転またはローリングについては、「顧客キーまたは利用可能なキーをロールまたは回転 [する」を参照してください](customer-key-availability-key-roll.md)。 DEP を更新してキーの新しいバージョンを使用する場合は、この記事で前述したように Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。

## <a name="related-articles"></a>関連記事:

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)
