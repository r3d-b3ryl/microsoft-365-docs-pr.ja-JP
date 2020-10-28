---
title: 顧客キーを設定する
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
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams の各ファイルに対して Microsoft 365 の顧客キーを設定する方法について説明します。
ms.openlocfilehash: be7aacf180cf8ffc59a490279083aeb2aa6a0567
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48768975"
---
# <a name="set-up-customer-key"></a>顧客キーを設定する

顧客キーを使用して、組織の暗号化キーを制御し、microsoft 365 を使用して Microsoft のデータセンターで保存されているデータを暗号化するように構成します。 言い換えると、顧客キーを使用すると、そのキーを使用して、ユーザーに属する暗号化の層を追加することができます。 保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。

Office 365 の顧客キーを使用するには、事前に Azure をセットアップする必要があります。 このトピックでは、必要な Azure リソースを作成して構成するために従う必要のある手順について説明し、Office 365 で顧客キーを設定する手順について説明します。 Azure のセットアップを完了した後、組織内のメールボックスとファイルに割り当てるポリシーとそのためのキーを決定します。 ポリシーを割り当てていないメールボックスとファイルでは、Microsoft によって制御および管理されている暗号化ポリシーが使用されます。 顧客キーの詳細、または一般的な概要については、「 [Office 2010 での顧客キーを使用したサービスの暗号化 365](customer-key-overview.md)」を参照してください。
  
> [!IMPORTANT]
> このトピックのベストプラクティスに従うことを強くお勧めします。 これらは、 **TIP** と **重要** と呼ばれます。 顧客キーを使用すると、組織全体でスコープが大きくなる可能性があるルート暗号化キーを制御できます。 このため、これらのキーに誤りが発生しても、サービスが中断したり、データが irrevocable 失われたりする可能性があります。
  
## <a name="before-you-set-up-customer-key"></a>顧客キーを設定する前に

開始する前に、組織の適切なライセンスがあること、およびアカウントが請求され、クレジットカードで支払いが行われないことを確認してください。 Microsoft 365 の顧客キーは、Office 365 E5 または Advanced コンプライアンス SKU で提供されます。 このトピックの概念と手順を理解するには、「 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 」のドキュメントを参照してください。 また、「 [テナント](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))」など、Azure で使用される用語について理解しておいてください。

このトピックの概念と手順を理解するには、「 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/) 」のドキュメントを参照してください。 また、「azure [AD テナント](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)」などの、azure で使用される用語について理解しておいてください。

FastTrack は、顧客キーの登録に使用する必要なテナントおよびサービス構成情報を収集するためにのみ使用されます。 カスタマーキー提供は FastTrack を通じて公開されるため、パートナーは同じ方法で必要な情報を送信することができます。 FastTrack を使用すると、提供されているデータのアーカイブも容易になります。
  
ドキュメント以外のサポートが必要な場合は、Microsoft コンサルティングサービス (MCS)、プレミアフィールドエンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。 ドキュメントなど、顧客キーに関するフィードバックを提供するために、アイデア、提案、および展望を customerkeyfeedback@microsoft.com に送信します。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>顧客キーを設定する手順の概要

顧客キーを設定するには、リストされている順序でこれらのタスクを完了します。 この記事の残りの部分では、各タスクの詳細な手順を説明します。または、プロセスの各手順に関する詳細情報へのリンクを示します。
  
**Azure と Microsoft FastTrack の場合:**
  
これらのタスクのほとんどは、Azure PowerShell にリモートで接続することで完了します。 最良の結果を得るには、Azure PowerShell のバージョン4.4.0 以降を使用します。
  
- [2つの新しい Azure サブスクリプションを作成する](#create-two-new-azure-subscriptions)

- [Azure サブスクリプションを登録して必須の保持期間を使用する](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  登録には 1 ~ 5 営業日かかります。

- [Office 365 の顧客キーを有効にするための要求を送信する](#submit-a-request-to-activate-customer-key-for-office-365)

2つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている web フォームに入力して、適切な顧客キー提示要求を送信する必要があります。 **FastTrack チームは、顧客キーについてサポートを提供していません。Office では、FastTrack ポータルを使用** してフォームを送信することができます。また、顧客キーの関連する提供を追跡するのに役立ちます。

- [各サブスクリプションにプレミアム Azure キーコンテナーを作成する](#create-a-premium-azure-key-vault-in-each-subscription)

- [各キーコンテナーにアクセス許可を割り当てる](#assign-permissions-to-each-key-vault)

- [キーコンテナーでの論理削除を有効にして、確認します。](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [キーの回復レベルを確認する](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault をバックアップする](#back-up-azure-key-vault)

- [Azure Key Vault 構成設定を検証する](#validate-azure-key-vault-configuration-settings)

- [各 Azure Key Vault キーの URI を取得する](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365:**
  
Exchange Online と Skype for Business:
  
- [Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [メールボックスに DEP を割り当てる](#assign-a-dep-to-a-mailbox)

- [メールボックスの暗号化を検証する](#validate-mailbox-encryption)

SharePoint Online と OneDrive for Business:
  
- [SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online、OneDrive for Business、および Teams ファイルのファイル暗号化を検証する](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure Key Vault のタスクを完了し、顧客キーの Microsoft FastTrack を管理する

Azure Key Vault でこれらのタスクを完了します。 これらの手順は、Exchange Online と Skype for business のどちらを使用するか、または Office 365 でサポートされているすべてのサービスに対して、顧客キーを設定するかどうかにかかわらず実行する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2つの新しい Azure サブスクリプションを作成する

顧客キーには2つの Azure サブスクリプションが必要です。 ベストプラクティスとして、Microsoft では、顧客キーと共に使用するために新しい Azure サブスクリプションを作成することをお勧めします。 Azure Key Vault キーは、同じ Azure Active Directory (Microsoft Azure Active Directory) テナント内のアプリケーションに対してのみ承認できます。 DEPs が割り当てられている組織で使用されているものと同じ Azure AD テナントを使用して、新しいサブスクリプションを作成する必要があります。 たとえば、組織内のグローバル管理者権限を持つ職場または学校のアカウントを使用します。 詳細な手順については、「 [組織としての Azure へのサインアップ](https://azure.microsoft.com/documentation/articles/sign-up-organization/)」を参照してください。
  
> [!IMPORTANT]
> 顧客キーには、データ暗号化ポリシー (DEP) ごとに2つのキーが必要です。 これを実現するためには、2つの Azure サブスクリプションを作成する必要があります。 ベストプラクティスとして、組織のメンバーごとに、各サブスクリプションで1つのキーを構成することをお勧めします。 さらに、これらの Azure サブスクリプションは、Office 365 の暗号化キーを管理するためにのみ使用してください。 これにより、オペレーターのいずれかが偶然、故意、または悪意によって削除された場合や、自分が責任を持つキーを誤って管理した場合に、組織が保護されます。
> 
> 顧客キーで使用するために Azure Key Vault リソースの管理にのみ使用される新しい Azure サブスクリプションをセットアップすることをお勧めします。 組織に対して作成できる Azure サブスクリプションの数に実際に制限はありません。 これらのベストプラクティスに従うことで、顧客キーによって使用されるリソースの管理を支援しながら、人的エラーの影響を最小限に抑えることができます。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Office 365 の顧客キーを有効にするための要求を送信する

Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)で提供要求を提出する必要があります。 FastTrack web ポータルを通じて要求を送信すると、Microsoft は、提供された Azure Key Vault 構成データと連絡先情報を検証します。 組織の承認済みの担当者に関する提供フォームで行う選択は、重要であり、顧客のキーの登録を完了するために必要です。 フォームで選択する組織の責任者は、顧客キーデータ暗号化ポリシーで使用されているすべてのキーを取り消して破棄するためのすべての要求の信頼性を確保するために使用されます。 この手順を1回実行する必要があります。これを行うには、Exchange Online と Skype for business の使用をサポートするための顧客キーを有効にし、SharePoint Online と OneDrive for business の顧客キーを再度アクティブにします。
  
顧客キーを有効にするオファーを提出するには、次の手順を実行します。
  
1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。

2. ログインしたら、 **ダッシュボード** を参照します。

3. ナビゲーションバーから [ **展開** ] を選択する **か、また** は **展開** 情報カードの [ **すべての展開リソースを表示** する] を選択して、現在のサービスの一覧を確認します。

4. 適用するオファーの情報カードを選択します。

   - **Exchange Online と Skype For business:****Exchange online オファーの要求暗号化キーのヘルプ** を選択します。

   - **SharePoint Online、OneDrive、Teams の各ファイル:** [ **Sharepoint および OneDrive オファーの要求の暗号化キーのヘルプ** ] を選択します。

5. オファーの詳細を確認したら、 **手順2に進み** ます。

6. 提供フォームで該当するすべての詳細と要求された情報を記入します。 暗号化キーとデータを永続的に、元に戻れないように承認する組織の責任者に対して、特定の選択について特に注目してください。 フォームが完成したら、[ **送信** ] を選択します。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure サブスクリプションを登録して必須の保持期間を使用する

ルート暗号化キーが一時的または完全に失われると、非常に破壊的または重大な操作によってデータが失われる可能性があります。 このため、顧客キーで使用されるリソースには強力な保護が必要です。 顧客キーと共に使用されるすべての Azure リソースは、既定の構成を超える保護メカニズムを提供します。 Azure サブスクリプションは、即時および irrevocable のキャンセルを防止するようにタグ付けまたは登録することができます。 これは、必須の保持期間の登録と呼ばれます。 必須の保持期間に Azure サブスクリプションを登録するために必要な手順については、Microsoft 365 チームとの共同作業が必要です。 このプロセスには、1 ~ 5 営業日かかることがあります。 以前は、これは「キャンセルしない」と呼ばれることがありました。
  
Microsoft 365 チームに連絡する前に、顧客キーで使用する Azure サブスクリプションごとに以下の手順を実行する必要があります。 開始する前に、 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストールされていることを確認してください。
  
1. Azure PowerShell でサインインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。

2. Register-AzProviderFeature コマンドレットを実行して、必須の保持期間を使用するようにサブスクリプションを登録します。 各サブスクリプションに対してこの操作を実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスを完了させるために、Microsoft にお問い合わせください。 SharePoint および OneDrive for Business チームについては、 [spock@microsoft.com](mailto:spock@microsoft.com)にお問い合わせください。 Exchange Online と Skype for Business の場合は、 [exock@microsoft.com](mailto:exock@microsoft.com)にお問い合わせください。 メールに次のものを含めます。

   **件名** : の顧客キー \<*Your tenant's fully-qualified domain name*\>

   **本文** : 必須の保持期間を最終処理するサブスクリプション id。
   各サブスクリプションの Get-AzProviderFeature の出力。

   このプロセスを完了するためのサービスレベル契約 (SLA) は、Microsoft が事前通知 (および検証) した後で、サブスクリプションを必須の保持期間を使用するように登録した後、5営業日です。

4. 登録が完了したことを Microsoft から通知されたら、次のように Get-AzProviderFeature コマンドを実行して、登録の状態を確認します。 検証された場合、Get-AzProviderFeature コマンドは、 **登録状態** プロパティに **登録さ** れている値を返します。 各サブスクリプションに対してこの操作を実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. プロセスを完了するには、Register-AzResourceProvider コマンドを実行します。 各サブスクリプションに対してこの操作を実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure キーコンテナーを作成する

キーコンテナーを作成する手順については、「azure [キーコンテナー](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の概要」で説明されています。このガイドでは、azure PowerShell のインストールと起動、azure サブスクリプションへの接続、リソースグループの作成、およびそのリソースグループでのキーコンテナーの作成を実行する方法について説明します。
  
キーコンテナーを作成する場合、SKU: Standard または Premium のどちらかを選択する必要があります。 標準 SKU を使用すると、Azure Key Vault キーがソフトウェアで保護されます。ハードウェアセキュリティモジュール (HSM) キー保護はありません。また、Premium SKU では、重要な資格情報のキーを保護するために Hsm を使用することができます。 顧客キーは、いずれかの SKU を使用するキーコンテナーを受け入れますが、Microsoft は Premium SKU のみを使用することを強くお勧めします。 どちらの種類のキーを使用する操作のコストも同じであるため、コストの唯一の違いは、各 HSM で保護されたキーの月ごとのコストです。 詳細については、「 [主要な資格情報](https://azure.microsoft.com/pricing/details/key-vault/) 」を参照してください。
  
> [!IMPORTANT]
> プレミアム SKU キーコンテナーおよび HSM で保護された、運用データ用のキーを使用して、テストおよび検証の目的で標準的な SKU キーボルトとキーのみを使用します。
  
顧客キーを使用する Microsoft 365 サービスごとに、作成した2つの Azure サブスクリプションのそれぞれにキーコンテナーを作成します。 たとえば、Exchange Online と Skype for business のみ、または SharePoint Online と OneDrive for business の場合のみ、ボルトのペアを1つだけ作成します。 Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キーコンテナーの2つのペアを作成します。
  
資格情報コンテナーを関連付けるためのデータ暗号化ポリシーの使用目的を反映する、キーコンテナーの名前付け規則を使用します。 命名規則の推奨事項については、以下の「ベストプラクティス」セクションを参照してください。
  
各データ暗号化ポリシーに対して、独立したコンテナーのセットを作成します。 Exchange Online の場合、データ暗号化ポリシーの範囲は、そのポリシーをメールボックスに割り当てるときに選択されます。 メールボックスに割り当てることのできるポリシーは1つだけで、最大50のポリシーを作成できます。 SharePoint Online では、ポリシーの範囲として、組織内のすべてのデータが地理的な場所または _geo_ に含まれます。

キーコンテナーの作成には、Azure リソースグループの作成も必要です。これは、キーコンテナーにはストレージ容量が必要です (非常に小さい)。また、キーヴォールトログが有効になっている場合は、保存されたデータも生成します。 ベストプラクティスとして、Microsoft では、個別の管理者を使用して各リソースグループを管理することをお勧めします。管理者は、関連するすべての顧客キーリソースを管理する一連の管理者と連携しています。
  
> [!IMPORTANT]
> 可用性を最大限にするには、Microsoft 365 サービスに近い地域にキーコンテナーが必要です。 たとえば、北米に Exchange Online 組織がある場合は、北アメリカにキーコンテナーを配置します。 Exchange Online 組織がヨーロッパの場合は、重要な資格を欧州に配置します。
> 
> キーコンテナーに共通のプレフィックスを使用します。また、重要な資格情報の使用およびスコープの省略形を含みます (たとえば、コンテナーが北米に配置される Contoso SharePoint サービスの場合は、名前の組み合わせが O365SP-NA-VaultA1 および O365SP-NA-VaultA2 になります。 コンテナー名は Azure 内のグローバルに一意の文字列なので、目的の名前が他の Azure のお客様によって既に要求されている場合は、目的の名前のバリエーションを試す必要があります。 2017年7月の資格情報を変更することはできません。そのため、セットアップに関する計画を作成し、2番目のユーザーを使用して計画が正常に実行されることを確認することをお勧めします。
> 
> 可能な場合は、ペアになっていない地域にコンテナーを作成します。 ペアになっている Azure 領域は、サービス障害ドメイン間で高可用性を提供します。 そのため、地域のペアは、互いのバックアップ地域と考えることができます。 これは、1つの領域に配置されている Azure リソースが、ペア化された領域を通じて自動的にフォールトトレランスを獲得することを意味します。 このため、領域がペアになっているデータ暗号化ポリシーで使用される2つの資格情報領域を選択すると、2つの空き領域が使用されることになります。 ほとんどの地域には2つの地域があるため、ペアになっていない地域を選択することはまだできません。 可能であれば、データ暗号化ポリシーで使用する2つの資格情報に対して2つのペアでない地域を選択します。 これは、合計4つの可用性の領域からメリットを得られます。 詳細については、「 [Business 継続性と障害復旧 (BCDR)](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 」を参照してください。現在の地域のペアの一覧については、「Azure ペアリング領域」を参照してください。
  
### <a name="assign-permissions-to-each-key-vault"></a>各キーコンテナーにアクセス許可を割り当てる

各キーコンテナーについて、お客様の実装に応じて、顧客キーに対して3つの個別のアクセス許可セットを定義する必要があります。 たとえば、次のいずれかのアクセス許可のセットを定義する必要があります。
  
- 組織のために主要な資格情報コンテナーの日常の管理を実行する **主要な資格情報コンテナー管理者** 。 これらのタスクには、backup、create、get、import、list、restore があります。

  > [!IMPORTANT]
  > キーコンテナー管理者に割り当てられているアクセス許可のセットには、キーを削除するためのアクセス許可は含まれていません。 これは意図的で重要な手法です。 暗号化キーの削除は、通常、データを完全に破棄するため、通常は行われません。 ベストプラクティスとして、既定では、このアクセス許可を主要な資格情報管理者に付与しないでください。 その代わりに、主要な資格情報投稿者に対してこれを予約し、その結果を明確に理解した後に、短い期間のみ管理者に割り当てるようにしてください。
  
  これらのアクセス許可を組織内のユーザーに割り当てるには、azure PowerShell を使用して Azure サブスクリプションにログインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。

- Set-AzKeyVaultAccessPolicy コマンドレットを実行して、必要なアクセス許可を割り当てます。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   以下に例を示します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure Key Vault 自体に対する権限を変更できる **重要な資格情報投稿** 者。 これらのアクセス許可を変更する必要があるのは、従業員がチームを脱退するか、チームに参加するか、重要な資格情報管理者がキーを削除または復元するためのアクセス許可を必要とする非常にまれな状況です。 この一連の主要なコンテナー投稿者は、キーコンテナーに対して **投稿者** の役割を付与する必要があります。 この役割は、Azure リソースマネージャーを使用して割り当てることができます。 詳細な手順については、「 [Role-Based のアクセス制御を使用して Azure サブスクリプションリソースへのアクセスを管理する](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)」を参照してください。 サブスクリプションを作成する管理者は、このアクセス権と、他の管理者を共同作成者の役割に割り当てることができます。

- 顧客キーを Exchange Online と Skype for business で使用する場合は、Exchange Online と Skype for business の代わりにキーコンテナーを使用するためのアクセス許可を Microsoft 365 に付与する必要があります。 同様に、SharePoint Online と OneDrive for business で顧客キーを使用する場合は、SharePoint Online と OneDrive for business の代わりにキーコンテナーを使用するために、Microsoft 365 のアクセス許可を追加する必要があります。 Microsoft 365 にアクセス許可を付与するには、次の構文を使用して **AzKeyVaultAccessPolicy** コマンドレットを実行します。 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   ここで、

    - [ *コンテナー名* は、作成したキーコンテナーの名前です。

    - Exchange Online と Skype for Business の場合は、  *Office 365 appID* をに置き換えます。 `00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online、OneDrive for Business、Teams の各ファイルについては、  *Office 365 appID* をに置き換えます。 `00000003-0000-0ff1-ce00-000000000000`

  例: Exchange Online と Skype for Business のアクセス許可を設定する:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  例: SharePoint Online、OneDrive for Business、Teams の各ファイルに対する権限の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>キーコンテナーでの論理削除を有効にして、確認します。

キーをすばやく回復できると、偶然または悪意によって削除されたキーによってサービスの停止が発生する可能性が低くなります。 ユーザーキーでキーを使用する前に、この構成を (ソフト削除と呼ばれる) 有効にする必要があります。 ソフト削除を有効にすると、バックアップからの復元を行わずに、削除から90日以内にキーまたは資格を回復できます。
  
キーコンテナーでの論理削除を有効にするには、次の手順を実行します。
  
1. Windows PowerShell を使用して、Azure サブスクリプションにサインインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。

2. [-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)コマンドレットを実行します。 この例では、次のように、ソフトウェアの削除を有効にするキーコンテナーの名前を *vault name* にします。

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **-AzKeyVault** コマンドレットを実行して、重要なコンテナーに対して論理削除が構成されていることを確認します。 重要なコンテナーに対して論理削除が適切に構成されている場合、 _ソフト削除が有効_ なプロパティは **True** の値を返します。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する

Azure Key Vault にキーを追加するには、2つの方法があります。キーを直接キーコンテナーに作成することも、キーをインポートすることもできます。 キーコンテナーに直接キーを作成することは、より単純な方法ですが、キーのインポートでは、キーの生成方法を完全に制御できます。 RSA キーを使用する必要があります。 Azure Key Vault は、楕円曲線キーを使用したラップとラップ解除をサポートしていません。
  
キーコンテナーに直接キーを作成するには、次のように [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) コマンドレットを実行します。
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

ここで、

- " *コンテナー名* " は、キーを作成するキーコンテナーの名前です。

- [ *キー名* には、新しいキーの名前を指定します。

  > [!TIP]
  > キーコンテナーの場合と同様の命名規則を使用して、名前付きキーを指定します。 このようにすると、キー名のみを表示するツールでは、文字列が自己記述されます。
  
- キーを HSM で保護する場合は、 _Destination_ パラメーターの値として **hsm** を指定する必要があります。そうでない場合は、 **ソフトウェア** を指定します。

例えば、
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

キーを直接キーコンテナーにインポートするには、nCipher nShield ハードウェアセキュリティモジュールを用意する必要があります。
  
一部の組織では、この方法を使用してキーの機能を確立し、次に示すこともできます。
  
- インポートに使用されるツールセットには、nCipher からの構成証明が含まれています。生成するキー交換キー (KEK) はエクスポート可能ではないため、nCipher によって製造された正規の HSM の内部で生成されます。

- ツールセットには、nCipher からの構成証明が含まれています。これは、Azure Key Vault セキュリティ world が nCipher で製造された正規の HSM でも生成されたことです。 この構成証明は、Microsoft が正規の nCipher ハードウェアを使用していることを証明します。

セキュリティグループに確認して、上記の attestations が必要かどうかを確認してください。 オンプレミスのキーを作成してキーコンテナーにインポートする詳細な手順については、「 [Azure Key vault 用に HSM で保護されたキーを生成して転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)」を参照してください。 各キーコンテナーにキーを作成するには、Azure の手順を使用します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 では、Azure Key Vault サブスクリプションがキャンセルされないように設定されており、顧客キーによって使用されるキーには、ソフト削除が有効になっている必要があります。 このことを確認するには、キーの回復レベルを参照してください。
  
キーの復旧レベルを確認するには、Azure PowerShell で、次のように Get-AzKeyVaultKey コマンドレットを実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

_回復レベル_ のプロパティが、回復 **可能 + ProtectedSubscription** の値以外を返す場合は、このトピックを確認して、サブスクリプションを [キャンセルしない] 一覧に追加し、各キーコンテナーでソフト削除が有効になっていることを確認する必要があります。
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault をバックアップする

作成またはキーへの変更の直後に、バックアップを実行し、オンラインとオフラインの両方でバックアップとストアのコピーを行います。 オフラインコピーは、物理的な安全または商用ストレージ機能などのネットワークに接続することはできません。 バックアップの少なくとも1つは、障害が発生した場合にアクセスできる場所に格納する必要があります。 バックアップ blob はキーマテリアルを復元するための唯一の手段です。キーコンテナーキーを完全に破棄するか、またはその他の方法で操作できないようにする必要があります。 Azure key vault の外部にあるキーは、キーを使用するために必要なメタデータが外部キーに存在しないため、バックアップとして認定されません。 顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。 したがって、キーをアップロードまたは作成した後に、Azure Key Vault のバックアップを作成することが重要です。
  
Azure Key Vault キーのバックアップを作成するには、次のように [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) コマンドレットを実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルがサフィックスを使用していることを確認し `.backup` ます。
  
このコマンドレットから得られる出力ファイルは暗号化されており、Azure Key Vault の外部では使用できません。 バックアップは、バックアップが実行された Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルに対して、コンテナー名とキー名の組み合わせを選択します。 これにより、ファイル名が自己記述されます。 バックアップファイルの名前が競合しないようにすることもできます。
  
以下に例を示します。
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 構成設定を検証する

DEP でキーを使用する前に検証を実行することはオプションですが、強くお勧めします。 特に、手順を使用して、このトピックで説明されているもの以外のキーとボルトを設定する場合は、顧客キーを構成する前に、Azure Key Vault のリソースの状態を検証する必要があります。
  
キーに get、wrapKey、および unwrapKey 操作が有効になっていることを確認するには、次の操作を行います。
  
次のようにして、次 [のコマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、必要に応じて、アクセスポリシーと Exchange Online id (GUID) または SharePoint Online id (GUID) を探します。 上記の3つのアクセス許可のすべてを [キーへのアクセス許可] の下に表示する必要があります。
  
アクセスポリシーの構成が正しくない場合は、次のように Set-AzKeyVaultAccessPolicy コマンドレットを実行します。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

たとえば、Exchange Online と Skype for Business の場合は次のようになります。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

たとえば、SharePoint Online と OneDrive for business の場合は次のようになります。
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

キーの有効期限が設定されていないことを確認するには、 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) コマンドレットを次のように実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

期限切れのキーを顧客キーで使用することはできず、期限切れのキーを使用して実行しようとした操作は失敗し、サービスが停止する可能性があります。 顧客キーと一緒に使用するキーに有効期限がないことを強くお勧めします。 有効期限日を設定すると、削除することはできませんが、別の日付に変更することができます。 有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を12/31/9999 に変更します。 有効期限が12/31/9999 以外の日付に設定されているキーは、Microsoft 365 検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限を変更するには、 [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) コマンドレットを次のように実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 顧客キーで使用する暗号化キーに有効期限を設定しないようにします。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

キーボルトを設定してキーを追加するために Azure のすべての手順を完了したら、次のコマンドを実行して、各キーコンテナーのキーの URI を取得します。 後で各 DEP を作成して割り当てるときにこれらの Uri を使用する必要があるので、この情報は安全な場所に保存しておいてください。 このコマンドは、キーヴォールトごとに1回実行してください。
  
Azure PowerShell の場合:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online と Skype for Business の顧客キーの設定

開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。 詳細については [、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 」を参照してください。
  
Exchange Online と Skype for Business の顧客キーを設定するには、Windows PowerShell を使用して Exchange Online にリモートで接続することにより、これらの手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。 Microsoft 365 のメールボックスに DEP を割り当てます。 その後、Microsoft 365 は、ポリシーで識別されたキーを使用して、メールボックスを暗号化します。 DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。 手順については [、「Azure Key Vault キーごとに URI を取得](#obtain-the-uri-for-each-azure-key-vault-key) する」を参照してください。
  
念頭! DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。 これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、次の手順を実行します。
  
1. ローカルコンピューターで、組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell ウィンドウで [Exchange Online powershell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) します。

2. DEP を作成するには、次のコマンドを入力して New-DataEncryptionPolicy コマンドレットを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、USA_mailboxes のようにします。

   - ポリシーの *説明* は、ポリシーの目的を記憶するのに役立つユーザーフレンドリなポリシーの説明です。 説明にはスペースを含めることができます。 たとえば、「米国およびその領土のメールボックスのルートキー」と入力します。

   - *KeyVaultURI1* は、ポリシー内の最初のキーの URI です。 たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> のようにします。

   - *KeyVaultURI2* は、ポリシーの2番目のキーの URI です。 たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> のようにします。 2つの Uri をコンマとスペースで区切ります。

   例: 
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

構文およびパラメーターの詳細については、「 [New-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)」を参照してください。

### <a name="assign-a-dep-to-a-mailbox"></a>メールボックスに DEP を割り当てる

Set-Mailbox コマンドレットを使用して、メールボックスに DEP を割り当てます。 ポリシーを割り当てた後、Microsoft 365 は DEP で指定されたキーを使用してメールボックスを暗号化することができます。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

ここで、 *MailboxIdParameter* はメールボックスを指定します。 Set-Mailbox コマンドレットの詳細については、「 [メールボックスの設定](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。

[ハイブリッド先進認証で iOS および Android 用の Outlook を使用しているオンプレミスのメールボックス](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)の場合、Exchange Online テナントに同期される社内メールボックスのデータは Set-MailUser コマンドレットを使用して DEP に割り当てることができます。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

ここで、 *Mailuseridparameter* はメールユーザー (メールが有効なユーザーとも呼ばれます) を指定します。 Set-MailUser コマンドレットの詳細については、「 [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)」を参照してください。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化を検証する

メールボックスを暗号化するには、しばらく時間がかかることがあります。 初めてのポリシーの割り当ての場合、メールボックスは、サービスがメールボックスを暗号化する前に、あるデータベースから別のデータベースに完全に移動する必要があります。 DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。
  
Get-MailboxStatistics コマンドレットを使用して、メールボックスが暗号化されているかどうかを判断します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true** の値を返し、メールボックスが暗号化されていない場合は **false** の値を返します。

メールボックスの移動が完了するまでの時間は、最初に DEP を割り当てるメールボックスの数、およびメールボックスのサイズによって異なります。 DEP を割り当てたときから1週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online、OneDrive for Business、および Teams ファイルの顧客キーの設定

開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。 詳細については [、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 」を参照してください。
  
SharePoint Online、OneDrive for Business、および Teams ファイル用の顧客キーを設定するには、Windows PowerShell を使用して SharePoint Online にリモートで接続することにより、これらの手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に格納されているキーのセットに関連付けられます。 1つの地理的な場所 (geo とも呼ばれます) 内のすべてのデータに DEP を適用します。 Office 365 の複数地域機能を使用する場合は、geo ごとに1つの DEP を作成して、各 geo ごとに異なるキーを使用することができます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams の各ファイルで使用するために、組織内に1人の DEP を作成できます。 Microsoft 365 は、DEP で識別されたキーを使用して、その地域のデータを暗号化します。 DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。 手順については [、「Azure Key Vault キーごとに URI を取得](#obtain-the-uri-for-each-azure-key-vault-key) する」を参照してください。
  
念頭! DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。 これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。
  
DEP を作成するには、Windows PowerShell を使用して SharePoint Online にリモートで接続する必要があります。
  
1. ローカルコンピューターで、組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [SharePoint Online PowerShell に接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)します。

2. Microsoft SharePoint Online 管理シェルで、Register-SPODataEncryptionPolicy コマンドレットを次のように実行します。

   ```powershell
   Register-SPODataEncryptionPolicy -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```
   例: 
  
 ```powershell
Register-SPODataEncryptionPolicy -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
```

   DEP を登録すると、暗号化は geo のデータに対して開始されます。 これには、しばらく時間がかかることがあります。 このパラメーターの使用の詳細については、「 [get-spodataencryptionpolicy](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps)」を参照してください。

### <a name="validate-file-encryption"></a>ファイルの暗号化を検証する

 SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには、 [Sharepoint Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)してから、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。 Customer キーの暗号化が有効になっており、すべてのサイトのすべてのファイルが暗号化されている場合、 _State_ プロパティは、 **登録** された値を返します。 暗号化がまだ実行中の場合、このコマンドレットは、完了したサイトの割合に関する情報を提供します。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーを管理する](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーについて](customer-key-availability-key-understand.md)

- [サービス暗号化](office-365-service-encryption.md)
