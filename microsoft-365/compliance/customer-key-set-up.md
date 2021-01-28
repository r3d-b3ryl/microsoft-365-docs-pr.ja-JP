---
title: アプリケーション レベルで顧客キーをセットアップする
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
description: Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーをセットアップする方法について説明します。
ms.openlocfilehash: 94702cecb37686c3996c5ed70b1810a825bb2ff6
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032614"
---
# <a name="set-up-customer-key-at-the-application-level"></a>アプリケーション レベルで顧客キーをセットアップする

顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft のデータ センターで保存されているデータを暗号化するために使用する Microsoft 365 を構成します。 つまり、顧客キーを使用すると、顧客は自分のキーを使用して、顧客に属する暗号化のレイヤーを追加できます。 保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。

顧客キーを 365 用に使用する前に、Azure をOfficeがあります。 この記事では、必要な Azure リソースを作成および構成するために従う必要がある手順について説明し、Office 365 で顧客キーを設定する手順を示します。 Azure のセットアップが完了したら、組織内のメールボックスとファイルに割り当てるポリシーとキーを決定します。 ポリシーを割り当てないメールボックスとファイルは、Microsoft によって制御および管理される暗号化ポリシーを使用します。 顧客キーの詳細、または一般的な概要については、「顧客キーを使用したサービスの暗号化」を参照してください。Office [365](customer-key-overview.md).
  
> [!IMPORTANT]
> この記事のベスト プラクティスに従ってください。 これらはヒントと重要 **として** 呼び **出されます**。 顧客キーを使用すると、組織全体と同じ大きなスコープを持つルート暗号化キーを制御できます。 つまり、これらのキーの間違いは広範な影響を与える可能性があります。サービスが中断したり、データが取り消し可能な損失を引き起こす可能性があります。
  
## <a name="before-you-set-up-customer-key"></a>顧客キーを設定する前に

開始する前に、組織に適したライセンスを持っている必要があります。 サブスクリプションまたはクラウド サービス プロバイダーを使用して、有料マイクロソフトエンタープライズ契約 Azure サブスクリプションを使用します。 [お支払い方法] プランまたはクレジット カードを使用して購入した Azure サブスクリプションは、顧客キーではサポートされていません。 2020 年 4 月 1 日から、Office 365 のカスタマー キーは、Office 365 E5、M365 E5、M365 E5 コンプライアンス、M365 E5 情報保護 & ガバナンス SKU で提供されます。 Office 365 Advanced Compliance SKU は、新しいライセンスの調達には使用できなくなりました。 既存の Office 365 Advanced Compliance ライセンスは引き続きサポートされます。

この記事の概念と手順を理解するには [、Azure Key Vault のドキュメントを確認](https://docs.microsoft.com/azure/key-vault/) してください。 また、Azure テナントなど、Azure で使用される用語 [ADします](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)。

FastTrack は、顧客キーの登録に使用される必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。 顧客キーオファーは FastTrack 経由で公開され、お客様とパートナーが同じ方法で必要な情報を送信する際に便利です。 FastTrack では、オファーで提供したデータを簡単にアーカイブできます。
  
ドキュメント以外のサポートが必要な場合は、Microsoft Consulting Services (MCS)、Premier Field Engineering (PFE)、または Microsoft パートナーにお問い合わせください。 ドキュメントを含む顧客キーに関するフィードバックを提供するには、アイデア、提案、視点を顧客にcustomerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>顧客キーを設定する手順の概要

顧客キーを設定するには、これらのタスクを記載されている順序で完了します。 この記事の残りの部分では、各タスクの詳細な手順を示します。または、プロセスの各手順に関する詳細な情報にリンクします。
  
**Azure と Microsoft FastTrack の場合:**
  
これらのタスクの大部分は、Azure PowerShell にリモートで接続することで完了します。 最善の結果を得る場合は、Azure PowerShell のバージョン 4.4.0 以降を使用してください。
  
- [2 つの新しい Azure サブスクリプションを作成する](#create-two-new-azure-subscriptions)

- [Azure サブスクリプションを登録して必須の保持期間を使用する](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  登録には 1 ~ 5 営業日かかる場合があります。

- [365 年 365 日に顧客キーをライセンス認証Office送信する](#submit-a-request-to-activate-customer-key-for-office-365)

2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている Web フォームを完了して、適切な顧客キーの提供要求を送信する必要があります。 **FastTrack チームは、カスタマー キーのサポートを提供します。Office FastTrack** ポータルを使用するだけで、フォームを提出し、顧客キーの関連するオファーを追跡するのに役立ちます。

- [各サブスクリプションでプレミアム Azure Key Vault を作成する](#create-a-premium-azure-key-vault-in-each-subscription)

- [各キー コンテナーにアクセス許可を割り当てる](#assign-permissions-to-each-key-vault)

- [キー コンテナーで回復可能な削除を有効にして確認する](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [キーを作成またはインポートして、各キー コンテナーにキーを追加する](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [キーの回復レベルを確認する](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault をバックアップする](#back-up-azure-key-vault)

- [Azure Key Vault の構成設定を検証する](#validate-azure-key-vault-configuration-settings)

- [各 Azure Key Vault キーの URI を取得する](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365:**
  
Exchange Online と Skype for Business:
  
- [Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [メールボックスに DEP を割り当てる](#assign-a-dep-to-a-mailbox)

- [メールボックスの暗号化を検証する](#validate-mailbox-encryption)

SharePoint Online と OneDrive for Business:
  
- [SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online、OneDrive for Business、および Teams ファイルのファイル暗号化を検証する](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する

Azure Key Vault でこれらのタスクを完了します。 これらの手順は、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams のファイル、または Office 365 でサポートされているサービスのカスタマー キーを設定する予定かどうかに関係なく実行する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

顧客キーには 2 つの Azure サブスクリプションが必要です。 ベスト プラクティスとして、顧客キーで使用する新しい Azure サブスクリプションを作成するようにお勧めします。 Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションにのみ承認できます。DEP が割り当てられる組織と同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。 たとえば、組織内のグローバル管理者特権を持つ、仕事用または学校用のアカウントを使用する場合などです。 詳細な手順については、「 [組織として Azure にサインアップする」を参照してください](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 顧客キーには、データ暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、組織の個別のメンバーがサブスクリプションごとに 1 つのキーを構成する方法をお勧めします。 これらの Azure サブスクリプションは、Azure 365 の暗号化キーを管理する場合にのみOfficeしてください。 これにより、オペレーターの 1 人が誤って、意図的に、または悪意を持って削除したり、責任を負うキーを誤って管理したりした場合に、組織を保護します。
>

組織で作成できる Azure サブスクリプションの数に実際的な制限はありません。 これらのベスト プラクティスに従って、カスタマー キーで使用されるリソースを管理しながら、人的エラーの影響を最小限に抑えます。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>365 年 365 日に顧客キーをライセンス認証Office送信する

Azure の手順を完了したら、Microsoft FastTrack ポータルでオファー要求を [送信する必要があります](https://fasttrack.microsoft.com/)。 FastTrack Web ポータルから要求を送信すると、Microsoft は指定した Azure Key Vault 構成データと連絡先情報を確認します。 組織の承認された責任者に関するオファー フォームでの選択は、顧客キーの登録を完了するために重要で必要です。 組織の責任者は、顧客キーデータの暗号化ポリシーで使用されるキーを取り消して破棄する要求の信頼性を確保します。 この手順は、Exchange Online および Skype for Business の対象範囲の顧客キーをアクティブ化するために 1 回だけ行い、もう 1 回は SharePoint Online と OneDrive for Business のカスタマー キーをアクティブ化する必要があります。
  
顧客キーをアクティブ化するオファーを提出するには、次の手順を実行します。
  
1. 組織でグローバル管理者のアクセス許可を持つ、仕事または学校のアカウントを使用して [、Microsoft FastTrack ポータルにサインインします](https://fasttrack.microsoft.com/)。

2. ログインしたら、ダッシュボードを参照 **します**。

3. ナビゲーション **バーから [** 展開]  **を選択するか**、[情報カードの展開] ですべての展開リソースを表示するを選択し、現在のオファーの一覧を確認します。

4. 該当するオファーの情報カードを選択します。

   - **Exchange Online と Skype for Business:** Exchange オンライン オファー **の暗号化キーのヘルプを要求するを選択** します。

   - **SharePoint Online、OneDrive、および Teams のファイル:** Sharepoint と **OneDrive の提供の暗号化キーのヘルプを要求するを選択** します。

5. オファーの詳細を確認したら、[手順 2 に進む] **を選択します**。

6. 該当する詳細情報と要求された情報をオファー フォームに入力します。 暗号化キーとデータの永続的で取り返しのつまらない破棄を承認するために承認する組織の役員の選択に特に注意を払います。 フォームが完成したら、[送信] を選択 **します**。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure サブスクリプションを登録して必須の保持期間を使用する

ルート暗号化キーが一時的または永続的に失われると、サービス操作が中断したり、致命的な障害が発生したり、データが失われる可能性があります。 このため、顧客キーで使用されるリソースには強力な保護が必要です。 顧客キーと一緒に使用される Azure リソースはすべて、既定の構成を超える保護メカニズムを提供します。 Azure サブスクリプションには、必須の保持期間のタグ *を付けまたは登録できます*。 必須の保持期間を指定すると、Azure サブスクリプションの取り消しを即時および取り消し可能にできません。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順には、Microsoft 365 チームとの共同作業が必要です。 このプロセスには 1 ~ 5 営業日かかる場合があります。 以前は、必須の保持期間を "キャンセルしない" と呼ばれる場合があります。
  
Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに次の手順を実行する必要があります。 開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。
  
1. Azure PowerShell でサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. Register-AzProviderFeatureコマンドレットを実行して、必須の保持期間を使用するためにサブスクリプションを登録します。 サブスクリプションごとにこのアクションを完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスを完了するには、Microsoft にお問い合わせください。 SharePoint および OneDrive for Business チームの場合は、お問い合[spock@microsoft.com。](mailto:spock@microsoft.com) Exchange Online および Skype for Business の場合は、お問い合[exock@microsoft.com。](mailto:exock@microsoft.com) メールに次の情報を含める。

   **件名**: 顧客キー \<*Your tenant's fully qualified domain name*\>

   **本文**: 必須の保持期間を完了するサブスクリプションの ID と、各サブスクリプションの Get-AzProviderFeature出力を含める。

   このプロセスを完了するサービス レベル 契約 (SLA) は、サブスクリプションを登録して必須の保持期間を使用したと Microsoft に通知 (および検証) が完了した 5 営業日後です。

4. 登録が完了したという通知を Microsoft から受け取った後、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 確認された場合、Get-AzProviderFeatureコマンドは Registration State プロパティの **Registered** の値 **を返** します。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. プロセスを完了するには、次のコマンドRegister-AzResourceProviderします。 サブスクリプションごとにこの手順を完了します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションでプレミアム Azure Key Vault を作成する

キー コンテナーを作成する手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の使用を開始する」に記載されています。この手順では、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループでのキー コンテナーの作成について説明します。
  
キー コンテナーを作成する場合は、SKU (Standard または Premium) を選択する必要があります。 Standard SKU を使用すると、Azure Key Vault キーをソフトウェアで保護できます。ハードウェア セキュリティ モジュール (HS) キー保護はありません。また、Premium SKU では、キー コンテナー キーの保護に HSM を使用できます。 カスタマー キーは、いずれかの SKU を使用するキー コンテナーを受け入れるが、Premium SKU のみを使用する方法を強く推奨している。 どちらの種類のキーも操作のコストは同じなので、コストの唯一の違いは、各HSM で保護されたキーの 1 か月あたりのコストです。 詳細 [については、Key Vault の価格](https://azure.microsoft.com/pricing/details/key-vault/) を参照してください。
  
> [!IMPORTANT]
> Premium SKU キー コンテナーと、実稼働データに対して SKU で保護されたキーを使用し、テストと検証の目的には Standard SKU キー コンテナーとキーのみを使用します。
  
顧客キーを使用する Microsoft 365 サービスごとに、作成した 2 つの Azure サブスクリプションのそれぞれにキー コンテナーを作成します。 たとえば、Exchange Online と Skype for Business のみ、または SharePoint Online と OneDrive for Business の場合は、1 組のコンテナーのみを作成します。 Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キー コンテナーの 2 つのペアを作成します。
  
コンテナーを関連付ける DEP の使用目的を反映するキー コンテナーの名前付け規則を使用します。 名前付け規則の推奨事項については、以下の「ベスト プラクティス」セクションを参照してください。
  
データ暗号化ポリシーごとに個別のペアのコンテナーのセットを作成します。 Exchange Online では、メールボックスにポリシーを割り当てるときに、データ暗号化ポリシーのスコープが選択されます。 メールボックスに割り当て可能なポリシーは 1 つだけで、最大 50 のポリシーを作成できます。 SharePoint Online ポリシーの範囲には、地理的な場所 _(geo)_ 内の組織内のすべてのデータが含まれます。

キー コンテナーを作成するには Azure リソース グループの作成も必要です。キー コンテナーにはストレージ容量 (小さい場合) と Key Vault のログ記録 (有効な場合) も保存データが生成される必要があります。 ベスト プラクティスとして、関連する顧客キーリソースを管理する管理者のセットに合わせて管理を行い、個別の管理者を使用して各リソース グループを管理します。
  
> [!IMPORTANT]
> 可用性を最大限に高め、キー コンテナーは Microsoft 365 サービスに近い地域に保管する必要があります。 たとえば、Exchange Online 組織が北米にある場合は、キー コンテナーを北米に配置します。 Exchange Online 組織がヨーロッパにある場合は、主要なコンテナーをヨーロッパに配置します。
> 
> キー コンテナーに共通のプレフィックスを使用し、キー コンテナーとキーの使用とスコープの省略形を含める (たとえば、コンテナーが北アメリカに置く Contoso SharePoint サービスの場合、名前のペアとして Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 が考えられる)。 コンテナー名は Azure 内でグローバルに一意の文字列なので、目的の名前が他の Azure ユーザーによって既に要求されている場合に、目的の名前のバリエーションを試す必要がある場合があります。 2017 年 7 月のコンテナー名は変更できないので、ベスト プラクティスは、セットアップの計画を作成し、2 番目のユーザーを使用して計画が正しく実行されていることを確認する方法です。
> 
> 可能であれば、ペアでない地域にコンテナーを作成します。 ペアの Azure リージョンは、サービス 障害ドメイン間で高可用性を提供します。 したがって、地域のペアは互いにバックアップ地域と考え合う可能性があります。 つまり、1 つの地域に配置された Azure リソースは、ペアリングされた地域を通じて自動的にフォールト トレランスを取得します。 このため、地域がペアのデータ暗号化ポリシーで使用される 2 つのコンテナーに対して地域を選択すると、合計で 2 つの可用性の地域だけが使用されます。 ほとんどの地域には 2 つの地域しか存在しないので、ペアリングされていない地域をまだ選択できません。 可能であれば、データ暗号化ポリシーで使用する 2 つのコンテナーに対して、ペアではない 2 つの地域を選択します。 これにより、合計で 4 つの可用性の領域を利用できます。 詳細については、「ビジネス継続性と障害復旧 [(BCDR): 地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) ペアの現在の一覧については、Azure のペアリングされた地域」を参照してください。
  
### <a name="assign-permissions-to-each-key-vault"></a>各キー コンテナーにアクセス許可を割り当てる

実装に応じて、キー コンテナーごとに 3 つの異なるアクセス許可セットを定義する必要があります。 たとえば、次のそれぞれに対して 1 つのアクセス許可セットを定義する必要があります。
  
- **組織のキー** コンテナーを毎日管理するキー コンテナー管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、および復元が含まれます。

  > [!IMPORTANT]
  > キー コンテナー管理者に割り当てられた一連のアクセス許可には、キーを削除するアクセス許可は含められていない。 これは意図的で重要な方法です。 暗号化キーを削除すると、データが完全に破棄されるので、通常は削除しません。 ベスト プラクティスとして、このアクセス許可をキー コンテナー管理者に既定で付与することはお使いください。 代わりに、主要なコンテナーの投稿者のためにこれを予約し、結果の明確な理解が得られると、短期的に管理者に割り当てる必要があります。
  
  組織内のユーザーにこれらのアクセス許可を割り当てるには、Azure PowerShell を使用して Azure サブスクリプションにサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

- 必要なアクセスSet-AzKeyVaultAccessPolicy割り当てるには、次のコマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   次に、例を示します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure Key **Vault 自体の** アクセス許可を変更できる主要なコンテナーの投稿者。 従業員がチームから退出またはチームに参加する場合は、これらのアクセス許可を変更する必要があります。 キー コンテナー管理者がキーを削除または復元するためのアクセス許可を正当に必要とするまれな状況では、アクセス許可を変更する必要があります。 この一連の主要なコンテナー投稿者には、キー コンテナーの **共同作成者ロール** が付与されている必要があります。 このロールは、Azure リソース マネージャーを使用して割り当てできます。 詳細な手順については、「Role-Based Access Control を使用して Azure サブスクリプション リソースへのアクセス [を管理する」を参照してください](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。 サブスクリプションを作成する管理者は、このアクセス権を暗黙的に持ち、他の管理者を投稿者ロールに割り当てる機能を持っています。

- Exchange Online および Skype for Business で顧客キーを使用する場合は、Exchange Online と Skype for Business の代わりにキー コンテナーを使用するためのアクセス許可を Microsoft 365 に付与する必要があります。 同様に、SharePoint Online と OneDrive for Business で顧客キーを使用する場合は、Microsoft 365 が SharePoint Online と OneDrive for Business の代わりにキー コンテナーを使用するためのアクセス許可を追加する必要があります。 Microsoft 365 へのアクセス許可を付与するには、次の構文を使用して **Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   ここで、

    - *コンテナー名* は、作成したキー コンテナーの名前です。

    - Exchange Online と Skype for Business の場合は、Office  *365 appID* を `00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online、OneDrive for Business、および Teams のファイルの場合は  *、365 appID* Office置き換える `00000003-0000-0ff1-ce00-000000000000`

  例: Exchange Online と Skype for Business のアクセス許可の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  例: SharePoint Online、OneDrive for Business、および Teams ファイルのアクセス許可の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キー コンテナーで回復可能な削除を有効にして確認する

キーをすばやく回復できると、誤ってまたは悪意を持って削除されたキーが原因でサービスの停止が長く発生する可能性は低い可能性があります。 顧客キーでキーを使用する前に、この構成 (回復可能な削除と呼ばれる) を有効にする必要があります。 回復可能な削除を有効にすると、削除から 90 日以内に、キーまたはコンテナーをバックアップから復元することなく復元できます。
  
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

Azure Key Vault にキーを追加するには 2 つの方法があります。Key Vault で直接キーを作成するか、キーをインポートできます。 キーコンテナーで直接キーを作成する方法は複雑ではありません。一方、キーをインポートすると、キーの生成方法を完全に制御できます。 RSA キーを使用します。 Azure Key Vault では、楕円曲線キーの折り返しと折り返し解除はサポートされていません。
  
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

キー コンテナーにキーを直接インポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。
  
一部の組織では、キーの証明を確立するためにこの方法を優先し、次の構成証明も提供します。
  
- インポートに使用するツールセットには、生成するキーの暗号化に使用されるキー交換キー (KEK) がエクスポート可能ではなく、nCipher によって製造された正規の WAS 内で生成される nCipher からの構成証明が含まれます。

- このツールセットには、nCipher によって製造された正規の VAULT で Azure Key Vault セキュリティワールドも生成されたという nCipher からの構成証明が含まれています。 この構成証明は、Microsoft が正規の nCipher ハードウェアも使用しているという証明です。

セキュリティ グループに確認して、上記の構成証明が必要かどうかを確認します。 オンプレミスでキーを作成し、キー コンテナーにインポートする詳細な手順については [、「Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)用に、VAULT で保護されたキーを生成して転送する方法」を参照してください。 Azure の手順を使用して、各キー コンテナーにキーを作成します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 では、Azure Key Vault サブスクリプションが [キャンセルしない] に設定され、顧客キーで使用されるキーの削除 (回復可能) が有効になっている必要があります。 キーの回復レベルを確認することで、サブスクリプションの設定を確認できます。
  
キーの回復レベルを確認するには、Azure PowerShell で次Get-AzKeyVaultKeyコマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

回復レベルのプロパティが **Recoverable+ProtectedSubscription** の値以外の値を返す場合は、サブスクリプションを [取り消し不可] リストに設定し、各キー コンテナーで回復可能な削除を有効にしてください。
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault をバックアップする

キーの作成または変更の直後に、バックアップを実行し、バックアップのコピーをオンラインとオフラインの両方で保存します。 オフライン コピーは、物理的な安全なストレージや商用ストレージ機能など、どのネットワークにも接続できません。 障害が発生した場合にアクセスできる場所に、バックアップの少なくとも 1 つのコピーを格納する必要があります。 バックアップ BLOB は、Key Vault キーが完全に破棄された場合や、他の方法で操作できない場合にキー マテリアルを復元する唯一の手段です。 Azure Key Vault の外部に存在し、Azure Key Vault にインポートされたキーは、顧客キーでキーを使用するために必要なメタデータが外部キーと一緒に存在しないので、バックアップとして修飾されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 そのため、キーをアップロードまたは作成した後で、Azure Key Vault のバックアップを作成する必要があります。
  
Azure Key Vault キーのバックアップを作成するには、 [次のように Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルでサフィックスが使用されている必要があります `.backup` 。
  
このコマンドレットによって生成された出力ファイルは暗号化され、Azure Key Vault の外部では使用できません。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルの場合は、コンテナー名とキー名の組み合わせを選択します。 これにより、ファイル名が自己記述的に記述されます。 また、バックアップ ファイル名が衝突しないことです。
  
次に、例を示します。
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault の構成設定を検証する

DEP でキーを使用する前の検証はオプションですが、強くお勧めします。 この記事で説明する手順以外の手順でキーとコンテナーをセットアップする場合は、顧客キーを構成する前に Azure Key Vault リソースの正常性を検証します。
  
キーが有効で、操作 `get` が有効 `wrapKey` になっている `unwrapKey` か確認するには、次の手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、必要に応じて、アクセス ポリシーと Exchange Online ID (GUID) または SharePoint Online ID (GUID) を探します。 上記の 3 つのアクセス許可はすべて、キーへのアクセス許可の下に表示する必要があります。
  
アクセス ポリシーの構成が正しくない場合は、次Set-AzKeyVaultAccessPolicyコマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、Exchange Online および Skype for Business の場合:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、SharePoint Online と OneDrive for Business の場合:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

キーに有効期限が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

顧客キーは、有効期限が切れたキーを使用することはできません。 期限切れのキーを使用して試行された操作は失敗し、サービスが停止する可能性があります。 顧客キーで使用するキーには有効期限日を設定することを強く推奨します。 有効期限を設定すると削除できませんが、別の日付に変更できます。 有効期限が設定されているキーを使用する必要がある場合は、有効期限の値を 9999 年 12 月 31 日に変更します。 有効期限が 12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには [、Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーに有効期限を設定しません。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

キー コンテナーをセットアップしてキーを追加したら、次のコマンドを実行して、各キー コンテナーのキーの URI を取得します。 これらの URI は、後で各 DEP を作成して割り当てる際に使用する必要があります。そのため、この情報は安全な場所に保存してください。 キー コンテナーごとにこのコマンドを 1 回実行します。
  
Azure PowerShell の場合:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online と Skype for Business の顧客キーの設定

始める前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細 [については、「顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Exchange Online にリモートで接続して、次の手順をWindows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online および Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。 DEP を Microsoft 365 のメールボックスに割り当てる。 その後、Microsoft 365 はポリシーで識別されたキーを使用してメールボックスを暗号化します。 DEP を作成するには、前に取得したキー コンテナー URI が必要です。 手順 [については、「Azure Key Vault キーごとに URI](#obtain-the-uri-for-each-azure-key-vault-key) を取得する」を参照してください。
  
覚えておいてください。 DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別々の Azure リージョンに作成します。
  
DEP を作成するには、次の手順を実行します。
  
1. ローカル コンピューターで、組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、次のウィンドウで [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShellします。

2. DEP を作成するには、次のコマンドをNew-DataEncryptionPolicyコマンドレットを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes。

   - *ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーに分かっているポリシーの説明です。 説明にスペースを含めることができます。 たとえば、"米国とその地域のメールボックスのルート キー" などです。

   - *KeyVaultURI1* は、ポリシーの最初のキーの URI です。 たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。

   - *KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。 たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。 2 つの URI はコンマとスペースで区切ります。

   例:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

構文およびパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスに DEP を割り当てる

メールボックスに DEP を割り当てるには、次のコマンドレットSet-Mailboxします。 ポリシーを割り当てると、Microsoft 365 は DEP で識別されたキーを使用してメールボックスを暗号化できます。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailboxIdParameter はユーザー* メールボックスを指定します。 コマンドレットの詳細については、「Set-Mailbox [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。

ハイブリッド環境では、Exchange Online テナントに同期されるオンプレミスのメールボックス データに DEP を割り当てできます。 この同期されたメールボックス データに DEP を割り当てるには、次のコマンドレットSet-MailUserします。 ハイブリッド環境のメールボックス データの詳細については、iOS および Android 用の Outlook とハイブリッドのモダン認証を使用したオンプレミスのメールボックス [を参照してください](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailUserIdParameter は、* メール ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。 このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化を検証する

メールボックスの暗号化には時間がかかる場合があります。 初めてポリシーを割り当てる場合は、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。 DEP を変更した後、または初めて DEP をメールボックスに割り当てる場合は、暗号化の検証を試みる前に 72 時間待機することをお勧めします。
  
メールボックスがGet-MailboxStatisticsを確認するには、次のコマンドレットを使用します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true、** メールボックスが暗号化されていない場合は **値 false** を返します。 メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数と、メールボックスのサイズによって異なります。 DEP を割り当てた時間から 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーの設定

始める前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。 詳細 [については、「顧客キーの Azure Key Vault と Microsoft FastTrack のタスクを完了する」](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーをセットアップするには、SharePoint Online にリモートで Windows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>SharePoint Online および OneDrive for Business geo ごとにデータ暗号化ポリシー (DEP) を作成する

DEP を Azure Key Vault に格納されているキーのセットに関連付ける。 DEP は、地域とも呼ばれる 1 つの地理的な場所のすべてのデータに適用します。 Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を持つ DEP を geo ごとに 1 つ作成できます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams ファイルで使用する DEP を組織内に 1 つ作成できます。 Microsoft 365 は DEP で識別されたキーを使用して、その geo 内のデータを暗号化します。 DEP を作成するには、前に取得したキー コンテナー URI が必要です。 手順 [については、「Azure Key Vault キーごとに URI](#obtain-the-uri-for-each-azure-key-vault-key) を取得する」を参照してください。
  
覚えておいてください。 DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。 地理的冗長性を確保するために、これらのキーを 2 つの別々の Azure リージョンに作成します。
  
DEP を作成するには、次のコマンドを使用して SharePoint Online にリモートWindows PowerShell。
  
1. ローカル コンピューターで、組織の全体管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、SharePoint Online PowerShell に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)。

2. Microsoft SharePoint Online 管理シェルで、次のようにRegister-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   例:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   DEP を登録すると、geo 内のデータに対して暗号化が開始されます。 暗号化には時間がかかる場合があります。 このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true)。

### <a name="validate-file-encryption"></a>ファイルの暗号化を検証する

 SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)に接続し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。 State _プロパティ_ は、顧客キーの暗号化が有効で、すべてのサイトのすべてのファイルが暗号化されている場合に、登録された値を返します。 暗号化がまだ進行中の場合、このコマンドレットは完了したサイトの割合に関する情報を提供します。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)
