---
title: 顧客キーの設定
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
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams のファイルに Microsoft 365 のカスタマー キーをセットアップする方法について説明します。
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845835"
---
# <a name="set-up-customer-key"></a>顧客キーの設定

顧客キーを使用すると、組織の暗号化キーを制御し、Microsoft のデータ センターに保存中のデータを暗号化するためにその暗号化キーを使用する Microsoft 365 を構成できます。 つまり、顧客キーを使用すると、顧客キーを使用して、ユーザーは属している暗号化のレイヤーをキーと共に追加することができます。 保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。

顧客キーを 365 の顧客キーを使用する前に、Azure Officeがあります。 このトピックでは、必要な Azure リソースを作成して構成するために必要な手順について説明し、Office 365 の顧客キーをセットアップする手順を説明します。 Azure のセットアップを完了すると、組織内のメールボックスとファイルに割り当てるポリシーとそのキーを確認します。 ポリシーを割り当てないメールボックスおよびファイルは、Microsoft により制御され管理される暗号化ポリシーを使用します。 顧客キーまたは一般的な概要については、「顧客キーによるサービスの暗号化 [」(Officeを参照してください](customer-key-overview.md)。
  
> [!IMPORTANT]
> このトピックのベスト プラクティスに従うことを強くお勧めします。 これらはヒントと重要**と呼****ばれれれです**。 顧客キーを使用すると、スコープを組織全体の大きくすることができます、ルート暗号化キーを制御できます。 つまり、これらのキーを使った間間の悪い影響は、広範な影響を与える可能性があるため、サービスが中断したり、データの取り戻しもしなおになる可能性があります。
  
## <a name="before-you-set-up-customer-key"></a>顧客キーを設定する前に

開始する前に、組織に適したライセンスが設定されていることを確認してください。 Microsoft 365 のカスタマー キーは、Office 365 E5 または高度な Compliance SKU で提供されています。 このトピックの概念と手順を理解するには [、Azure Key Vault のドキュメントを確認](https://docs.microsoft.com/azure/key-vault/) してください。 また、テナントなど、Azure で使用されている用語についても理解 [しておきましょう](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))。

FastTrack は、カスタマー キーの登録に使用される必要なテナントとサービス構成情報を収集するためにのみ使用されます。 カスタマー キー オファーは FastTrack を介して公開されるため、お客様およびパートナーは同じ方法で必要な情報を送信しに使います。 FastTrack を使用すると、提供されたデータを容易にプランにアーカイブできます。
  
ドキュメントを追加購入する必要がある場合は、Microsoft Consulting Services (MCS)、プレミア フィールド エンジニアリング (PFE)、または Microsoft パートナーにお問い合わせください。 ドキュメントなど、顧客キーに関するフィードバックを提供するには、アイデア、提案、およびドキュメントに視点customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>顧客キーの設定手順の概要

顧客キーを設定するには、これらのタスクを一覧された順番で実行します。 この記事の残りの部分では、各タスクの詳細な手順を示したり、プロセスの各手順に関する詳細な情報へのリンクを示したりします。
  
**Azure および Microsoft FastTrack 内:**
  
ここに示すタスクの大部分は、Azure PowerShell にリモートで接続して完了します。 最良の結果を返すには、Azure PowerShell のバージョン 4.4.0 以降を使用してください。
  
- [2 つの新しい Azure サブスクリプションを作成する](#create-two-new-azure-subscriptions)

- [必須の保持期間を使用するために Azure サブスクリプションを登録する](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  登録には、1 から 5 名の業日をかかります。

- [顧客キーをアクティブ化する要求を、65 日Office送信する](#submit-a-request-to-activate-customer-key-for-office-365)

2 つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされる Web フォームを入力して、適切なカスタマー キー オファー要求を提出する必要があります。 **FastTrack チームはカスタマー キーのサポートを提供していません。Office、FastTrack ポータルを使用するだけでフォームを送信できるようになると、カスタマー キーの関連オファーの追跡に役立ちます**。

- [各サブスクリプションにプレミアム Azure Key Vault を作成する](#create-a-premium-azure-key-vault-in-each-subscription)

- [それぞれの主要なキーが含含けたユーザーにアクセス許可を割り当てる](#assign-permissions-to-each-key-vault)

- [Key Vaults で soft 削除を有効にしてから確認する](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [キーを作成またはインポートして各キー インベールにキーを追加する](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [キーの回復レベルを確認する](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault のバックアップ](#back-up-azure-key-vault)

- [Azure Key Vault 構成設定の検証](#validate-azure-key-vault-configuration-settings)

- [各 Azure Key Vault キーの URI を取得する](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365:**
  
Exchange Online と Skype for Business:
  
- [Exchange Online および Skype for Business で使用するためのデータ暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [DEP をメールボックスに割り当てる](#assign-a-dep-to-a-mailbox)

- [メールボックスの暗号化の検証](#validate-mailbox-encryption)

SharePoint Online と OneDrive for Business:
  
- [SharePoint Online および OneDrive for Business の地域ごとにデータの暗号化ポリシー (DEP) を作成する](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online、OneDrive for Business、および Teams のファイルの暗号化を検証する](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>顧客キー用の Azure Key Vault と Microsoft FastTrack 内のタスクを完了する

Azure Key Vault でこれらのタスクを実行します。 Exchange Online および Skype for Business 向け、または SharePoint Online、OneDrive for Business、Teams ファイル用のカスタマー キーをセットアップするのか、または Office 365 でサポートされているサービスのいずれに対してカスタマー キーをセットアップするのかに関係なく、これらの手順を完了する必要があります。
  
### <a name="create-two-new-azure-subscriptions"></a>2 つの新しい Azure サブスクリプションを作成する

カスタマー キーには 2 つの Azure サブスクリプションが必要です。 ベスト プラクティスとして、カスタマー キーと使用する新しい Azure サブスクリプションを作成するのが推奨されます。 Azure Key Vault Keys は、同じ Azure Active Directory (AAD) テナントのアプリケーションに対してのみ承認可能です。DEP を割り当てる組織で使うものと同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。 たとえば、組織のグローバル管理者特権を持つ職場または学校のアカウントを使用します。 詳細な手順については、組織 [としての Azure 用登録に関するページをご覧ください](https://azure.microsoft.com/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 顧客キーには、データの暗号化ポリシー (DEP) ごとに 2 つのキーが必要です。 これを実現するには、2 つの Azure サブスクリプションを作成する必要があります。 ベスト プラクティスとして、サブスクリプションごとに 1 つのキーを組織のメンバーに個別に構成するのがベスト プラクティスです。 また、これらの Azure サブスクリプションは、現在のアプリケーションの暗号化キーを管理する場合Officeしてください。 これは、オペレーターの 1 つが意図的に削除したり、悪意をとって削除したり、責を必要とするキーを不正に削除したりした場合に組織を保護します。 <br/> 新しい Azure サブスクリプションを設定する場合、Azure Key Vault リソースの管理に関して、顧客キーと共に使用するのみで使用する新しい Azure サブスクリプションを設定する必要があります。 組織用に作成できる Azure サブスクリプションの数に対する実用的な制限はありません。 これらのベスト プラクティスに従うと、顧客キーで使用されるリソースを管理しながら、人的エラーによる影響を最小限に抑えます。
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>顧客キーをアクティブ化する要求を、65 日Office送信する

Azure の手順を完了したら [、Microsoft FastTrack](https://fasttrack.microsoft.com/)ポータルでプラン要求を提出する必要があります。 FastTrack Web ポータルから要求を送信すると、Microsoft は Azure Key Vault 構成データと入力した連絡先情報を確認します。 組織の承認されているオファーに関するプラン形式での選択は重要で、カスタマー キーの登録を完了するために必要なものが重要です。 フォームで選択した組織のオフイスは、顧客キー データの暗号化ポリシーで使用されるすべてのキーの取り消し要求の信頼性を確認するために使用されます。 このステップでは、Exchange Online および Skype for Business のカスタマー キーをアクティブ化し、SharePoint Online および OneDrive for Business の顧客キーをアクティブ化するために、2 回目の手順を実行する必要があります。
  
顧客キーをアクタクト化するためにオファーを提出するには、次の手順を実行します。
  
1. 組織のグローバル管理者権限を持つ職場または学校のアカウントを使用して [、Microsoft FastTrack ポータルにログインします](https://fasttrack.microsoft.com/)。

2. ログインした後、ダッシュボードを参照 **します**。

3. ナビゲーション **バーから** [展開] を選 **むか、展開** 情報 **カードで [** 展開用リソース **を** すべて表示] を選び、現在のプランの一覧を確認します。

4. 適用するプランの情報カードを選択します。

   - **Exchange Online と Skype for Business:** Exchange Online **プランの [暗号化を要求する] ヘルプを選択** します。

   - **SharePoint Online、OneDrive、および Teams のファイル:****SharePoint と OneDrive オファーに対する [要求暗号化キーのヘルプ] を選択**します。

5. プランの詳細を確認したら、[続行] を選択 **します**。

6. 該当する詳細情報や要求された情報をすべてプラン フォームに入力します。 暗号化キーやデータの完全および元に戻す破損を承認する必要がある組織のユーザーが選択内容を特に注意しておき、注意してください。 フォームが完成したら、[送信] を選択 **します**。

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>必須の保持期間を使用するために Azure サブスクリプションを登録する

ルート暗号化キーの一時的なまたは完全な切り損失は、サービスの操作に大きな破壊的な場合があります。その結果、データが失われる可能性があります。 このため、顧客キーと使用されるリソースでは強力な保護が必要です。 カスタマー キーと共に使うすべての Azure リソースは、既定の構成を上書きする保護メカニズムを提供します。 Azure サブスクリプションにタグを付けたり登録したりすることができます。このようにすると、即時にキャンセルできない取り消しを防ぐことができます。 これは、必須の保持期間の登録と呼ばれることをいう。 必須の保持期間用に Azure サブスクリプションを登録するために必要な手順では、Microsoft 365 チームとのコラボレーションが必要です。 このプロセスには、1 から 5 日の間でかかります。 以前は、これを "取り消し不可能" と呼じことでした。
  
Microsoft 365 チームに問い合わせる前に、顧客キーで使用する各 Azure サブスクリプションについて、次の手順を実行する必要があります。 開始する前に [、Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) モジュールがインストール済みです。
  
1. Azure PowerShell を使用してサインインします。 手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. Register-AzProviderFeature コマンドレットを実行してサブスクリプションを登録し、必須の保持期間を使用します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. プロセスの最終処理については、マイクロソフトにお問い合わせください。 SharePoint および OneDrive for Business チームの場合、メール アドレス [spock@microsoft.com](mailto:spock@microsoft.com)。 Exchange Online および Skype for Business の場合は、連絡先プロパティ[のexock@microsoft.com。](mailto:exock@microsoft.com) 電子メールに次のものを含めると、以下の情報が表示されます。

   **Subject**: Customer Key \<*Your tenant's fully-qualified domain name*\>

   **本文**: 必須の保持期間を設定する必要があるサブスクリプション ID。
   各サブスクリプションの Get-AzProviderFeature の出力。

   Microsoft に通知 (および検証済み) がサブスクリプションの必須の保持期間を登録した後、このプロセスを完了するためのサービス レベル アグリーメント (SLA) は 5 週間になります。

4. 登録が完了したことを Microsoft に通知したら、Get-AzProviderFeature コマンドを次のように実行して登録の状態を確認します。 確認すると、Get-AzProviderFeature コマンドは登録状態プロパティの **Registered** の値 **を返** します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 処理を完了するには、Register-AzResourceProvider コマンドを実行します。 サブスクリプションごとにこのアクションを実行します。

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>各サブスクリプションにプレミアム Azure Key Vault を作成する

キー コンベートを作成する手順は [、Azure Key Vault の](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)概要に説明されています。このドキュメントでは、Azure PowerShell のインストールと起動、Azure サブスクリプションへの接続、リソース グループの作成、そのリソース グループのキー バールトの作成について説明しています。
  
キー バウルトを作成するときには、Standard または Premium のどちらかの SKU を選択する必要があります。 標準の SKU では、Azure Key Vault キーをソフトウェアで保護することができます。ハードウェア セキュリティ モジュール (HSM) キー保護がないため、Premium SKU を使用することで Key Vault Key を保護できます。 顧客キーは、どちらの SKU を使用するキー ブラルトを受け入れますが、プレミアム SKU のみを使用するを強くお勧めします。 どちらの種類のキーを使用した操作のコストも同じなので、コストの違いは、HSM で保護された各キーに対するコストだけです。 詳細 [については、「Key Vault の価格」を](https://azure.microsoft.com/pricing/details/key-vault/) 参照してください。
  
> [!IMPORTANT]
> Premium SKU キーの書き込みキーに対しては、運用環境のデータに対して Standard SKU キーのベールトおよび HSM で保護されたキーを使用し、テストと検証を目的として標準の SKU キーのベールトおよびキーのみを使用します。
  
顧客キーを使用する Microsoft 365 の各サービスについて、作成した 2 つの Azure サブスクリプションのそれぞれに、キー ブラルトを作成します。 たとえば、Exchange Online と Skype for Business のみ、または SharePoint Online と OneDrive for Business のみでは、1 つのキーを作成するだけで作成されます。 Exchange Online と SharePoint Online の両方に対して顧客キーを有効にするには、キー コンテナーの 2 つのペアを作成します。
  
キーの読み取りに使用する、書き込み可能なキーのポリシーを使用するキー ストアには、命名規則を使用します。 規則に関する推奨事項については、以下のベスト プラクティスのセクションを参照してください。
  
データの暗号化ポリシーごとに、別のコンテルのセットを作成します。 Exchange Online では、ポリシーをメールボックスに割り当てるときにデータの暗号化ポリシーのスコープが選択されます。 メールボックスに割り当てられるポリシーは 1 つだけで、最大 10 つのポリシーを作成できます。 SharePoint Online の場合、ポリシーのスコープは、地理的な場所、または geo 内の組織内のすべてのデータ _です_。

キー コンテナーの作成では、Azure リソース グループを作成する必要もあります。Vault は、ストレージ容量 (非常に小さい場合) と Key Vault ログが有効な場合は、保存されたデータも生成します。 ベスト プラクティスとしては、すべての関連するカスタマー キー リソースを管理する管理者のセットに合う管理方法を使用して、各リソース グループの管理に個別の管理者を使用してください。
  
> [!IMPORTANT]
> 最大限の可用性を実現するために、お使いのキー ウォールトは Microsoft 365 サービスに近い地域に収まっていないようにしてください。 たとえば、Exchange Online 組織が北アメリカにいなってきは、キー ブラルトを北米に配置します。 Exchange Online 組織が 3E におりかない場合は、キー ウェールテットを Europe に配置します。<br/>キーのバルテの共通プレフィックスを使います。 キー コンテナーとキーのキーの使用範囲 (たとえば、北米に保存される Contoso SharePoint サービスの場合、名前のペアは Contoso-O365SP-NA-VaultA1 と Contoso-O365SP-NA-VaultA2 です) が含まれます。 Vault 名は Azure 内でグローバルに一意の文字列であるため、必要な名前が他の Azure 顧客から既に要求されている場合に、必要な名前のバリエーションを試してみてください。 2017 年 7 月のベールト名は変更できないため、ベスト プラクティスはセットアップ用の計画を作成し、2 人目の担当者を使用して計画が正しく実行することを確認することです。<br/>可能であれば、ペアリングされていない領域にあいつもお使いのブルトを作成します。 ペアリングされた Azure 地域は、サービス障害ドメイン間の高可用性を提供します。 そのため、地域のペアは、おそらいのバックアップ地域といえます。 つまり、1 つの地域に配置された Azure リソースは、ペアリングされた領域を通じてフォールト トレランスを自動的に取得します。 このため、地域がペアリングされている、データの暗号化ポリシーで使用される 2 つのコンテナーの地域を選択すると、2 つの地域の合計使用地域のみが使用されていることを意味しています。 ほとんどの地域には 2 つの地域しかないため、ペアリングされていない地域を選択することはできません。 可能な場合は、データの暗号化ポリシーで使用される 2 つのコンテナーに対して、ペアリングされていない 2 つの地域を選択します。 この場合、可用性の合計で 4 つの領域から得できると、この利点があります。 詳細については、ビジネスの [連続性と障害復旧 (BCDR): 現在の](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 地域ペアのリストのための Azure Paired Regions をご覧ください。
  
### <a name="assign-permissions-to-each-key-vault"></a>それぞれの主要なキーが含含けたユーザーにアクセス許可を割り当てる

実装に応じて、キー コントラルタごとに、カスタマー キーに対して 3 つの異なるアクセス許可セットを定義する必要があります。 たとえば、次のそれぞれに対して 1 セットのアクセス許可を定義する必要があります。
  
- **組織の Key Vault** の日常的な管理を行う Key Vault 管理者。 これらのタスクには、バックアップ、作成、取得、インポート、リスト、復元が含まれます。

  > [!IMPORTANT]
  > キー を削除するためのアクセス許可は、キーを削除するために必要なアクセス許可のセットには含まれません。 これは意図的な方法で、重要な方法です。 暗号化キーの削除は、データを完全に破破し破破し、通常は行われません。 ベスト プラクティスとして、既定ではキーの設定を主な管理者にこのアクセス許可を付与しないでください。 代わりに、キー資格情報の投稿者にこれを予約し、このことは、この後、その後、わかりやすいうえで短期的に管理者に割り当ててください。
  
  これらのアクセス許可を組織内のユーザーに割り当てるには、Azure PowerShell を使って Azure サブスクリプションにログインします。 手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

- Set-AzKeyVaultAccessPolicy コマンドレットを実行して、必要なアクセス許可を割り当てます。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   以下に例を示します。

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure Key **Vault 自体のアクセス許可**を変更できる Key Vault 投稿者。 従業員がチームを脱退したりチームに参加したりする場合や、キーキーの削除や復元にクォールト管理者がアクセス許可をうまく必要としていない状況では、多少ない状況で変更する必要があります。 キーの書き込み元のこのセットには、Key Vault の **Contributor** ロールが付与されている必要があります。 Azure リソース マネージャーを使用してこのロールを割り当てできます。 詳細な手順については、「役割ベースのアクセス [制御を使用した Azure サブスクリプション リソースへのアクセスの管理」を参照してください](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。 サブスクリプションを作成する管理者には、暗黙的にこのアクセス権と、他の管理者を投稿者ロールに割り当てる機能が付与されます。

- Exchange Online と Skype for Business でカスタマー キーを使用する場合、Exchange Online と Skype for Business の代わりに主要な取り消しを使用するためのアクセス許可を Microsoft 365 に与えなければならない場合があります。 同様に、SharePoint Online と OneDrive for Business でカスタマー キーを使用する場合は、Microsoft 365 で SharePoint Online と OneDrive for Business の代わりにキー ウェールトを使用するためのアクセス許可を追加する必要があります。 Microsoft 365 にアクセス許可を付与するには、次の **構文を使用して Set-AzKeyVaultAccessPolicy** コマンドレットを実行します。 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   ここで、

    - *Vault name* は、作成したキー フォルダーの名前です。

    - Exchange Online および Skype for Business の場合は、*アプリ ID Officeで置換*`00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online、OneDrive for Business、および Teams の各ファイルの場合 *、Office 365 アプリ ID に置き換え*`00000003-0000-0ff1-ce00-000000000000`

  例: Exchange Online と Skype for Business のアクセス許可の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  例: SharePoint Online、OneDrive for Business、および Teams ファイルのアクセス許可の設定:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Key Vaults で soft 削除を有効にしてから確認する

キーをすばやく回復できると、削除が終了したり、悪意によって削除されたキーが発生したりしたために、延長サービスの停止が発生する可能性は低くなります。 カスタマー キーでキーを使用する前に、削除削除と呼ばれるこの構成を有効にする必要があります。 削除後 90 日以内にキーまたは休日を復元できます。キーまたはキーをバックアップから復元する必要はありません。
  
キー ウォールトで Soft Delete を有効にするには、次の手順を完了します。
  
1. Windows PowerShell を使用して Azure サブスクリプションにサインインします。 手順については [、「Azure PowerShell を使用してサインインする」を参照してください](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。

2. [Get-AzKeyVault コマンドレットを実行](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)します。 この例では *、キー キー名* は、削除済みアイテム フォルダーへの削除を有効にしているキー バールの名前です。

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault**コマンドレットを実行して、キー ビルトに対して行う削除が構成されていることを確認します。 キー コンテナーに対して正しく構成されている場合 _、[Soft Delete Enabled] プロパティ_ は値 True を返 **します**。

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>キーを作成またはインポートして各キー インベールにキーを追加する

Azure Key Vault にキーを追加する方法は 2 つあります。キーをキー ブレールに直接作成するか、またはキーをインポートすることができます。 Key Vault で直接キーを作成するのは複雑な方法な方法なので、キーをインポートすることによって、キーの生成方法を総したコントロールを制御できます。
  
キー キーを直接作成するには、次のように [Add-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) を実行します。
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

ここで、

- *Vault 名* は、キーを作成するキー キーの名前です。

- *key name* is the name you want to give the new key.

  > [!TIP]
  > 前述のように、キーに似命名規則を使った名前キーを使います。 これにより、キー名だけが表示されるツールで文字列を説明します。
  
- HSM でキーを保護する場合は _、Destination_パラメーターの値として**HSM**を指定し、指定しない場合は Software を指定**してください**。

例えば、
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

キー バルテに直接キーをインポートするには、nCipher nShield ハードウェア セキュリティ モジュールが必要です。
  
組織によっては、キーの証明を確立するためにこの方法を使用している場合もあるので、この方法で次の機能も提供します。
  
- インポートに使うツールセットには、生成するキーを暗号化するために使用されるキー交換キー (KEK) はエクスポート不可能で、nCipher によって製造された正当な HSM 内部に生成された nCipher からの証明が含まれています。

- nCipher が製造した Genuine HSM 製造上でも Azure Key Vault のセキュリティの世界で生成された nCipher からの構成証明が含まれています。 この構成証明は、Microsoft がジェネレーター ハードウェアも使用しているかどうかを証明します。

セキュリティ グループに確認し、上記の構成証明が必要かどうかを確認してください。 オンプレミスでキーを作成し、キー バルテにインポートする詳細な手順については、Azure Key Vault の HSM で保護されたキーを生成し [転送する方法を参照してください](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。 Azure の手順を使用して、各キー ブォールトにキーを作成します。
  
### <a name="check-the-recovery-level-of-your-keys"></a>キーの回復レベルを確認する

Microsoft 365 では、Azure Key Vault サブスクリプションが [取り消し不可能] に設定され、Customer Key が使うキーで削除済みアイテムへの削除が有効になっている必要があります。 キーの回復レベルを確認するには、次の操作を行います。
  
キーの回復レベルを確認するには、Azure PowerShell で Get-AzKeyVaultKey コマンドレットを以下のように実行します。
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

回復レベル _のプロパティが_ **Recoverable + ProtectedSubscription**の値以外の値を返す場合は、このトピックを確認した後、サブスクリプションを [キャンセルしない] リストに登録するすべての手順を実行したことと、キー キービルトごとに回復可能な削除を有効にしたことを確認する必要があります。
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault のバックアップ

キーの作成または変更の直後に、バックアップと保存のコピーをオンラインとオフラインの両方で実行します。 物理的な安全または商用記憶域など、オフライン コピーはネットワークに接続してはなりません。 障害が発生した場合にアクセスできる場所に、少なくとも 1 つのバックアップのコピーを格納する必要があります。 バックアップ BLOB は、キー コンテナーのキーを完全に破悪したり、レンダリング不可能にする必要がある、キー コンテナー型の復元方法の単に使用される方法です。 Azure Key Vault の外部にあり、Azure Key Vault にインポートされたキーは、カスタマー キーがキーを使用するために必要なメタデータは外部キーとの間に存在しないので、バックアップとして認られることはありません。 カスタマー キーによる復元操作には、Azure Key Vault から行されたバックアップのみを使用できます。 したがって、キーがアップロードまたは作成された後に Azure Key Vault のバックアップを作成する必要があります。
  
Azure Key VaultKey キーのバックアップを作成するには [、Backup-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) を次のように実行します。

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

出力ファイルにサフィックスが使用されていることを確認してください `.backup` 。
  
このコマンドレットによって出力される出力ファイルは暗号化されているため、Azure Key Vault 以外では使用できません。 バックアップは、バックアップの取得元の Azure サブスクリプションにのみ復元できます。
  
> [!TIP]
> 出力ファイルでは、ベールト名とキー名の組み合わせを選択します。 これにより、ファイル名が自動的に説明されます。 また、バックアップ ファイル名が調整されないことを確認します。
  
以下に例を示します。
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 構成設定の検証

DEP でキーを使用する前に検証を実行するオプションはオプションですが、強くお勧めします。 特に、このトピックで説明されているキーと保書以外のものをセットアップする手順を使用する場合、カスタマー キーを構成する前に Azure Key Vault リソースの正常性を検証する必要があります。
  
キーの取得、ラップ キー、および unwrapKey 操作が有効になっていることを確認するには、次の手順を実行します。
  
[Get-AzKeyVault コマンドレットを次](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)のように実行します。
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

出力で、アクセス ポリシー、Exchange Online ID (GUID)、または SharePoint Online ID (GUID) を適当に検索します。 上記 3 つのアクセス許可のうち、上記の 3 つすべてが [キーへのアクセス許可] 下に表示されている必要があります。
  
アクセス ポリシー構成が正しくない場合は、Set-AzKeyVaultAccessPolicy コマンドレットを次のように実行します。
  
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

キーに有効期限日が設定されていないことを確認するには、次のように [Get-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) を実行します。
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

期限切れのキーを顧客キーで使用すると、有効期限が切れたキーを使用しようとすると失敗し、場合によってサービスが停止します。 カスタマー キーと使用されるキーに有効期限がないことを強くお勧めします。 設定すると、有効期限は削除できませんが、別の日付に変更できます。 有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を 12/31/9999 に変更します。 有効期限が 9999 年 12 月 31 日を超える日付に設定されたキーは、Microsoft 365 の検証に合格しません。
  
12/31/9999 以外の値に設定されている有効期限日を変更するには [、Update-AzKeyVaultKey コマンドレット](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) を次のように実行します。
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> カスタマー キーで使用する暗号化キーに有効期限を設定しない。
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>各 Azure Key Vault キーの URI を取得する

Azure ですべての手順を完了し、キー バールをセットアップしてキーを追加したら、次のコマンドを実行して、キーの URI を各キー ビルトに取得します。 後で各 DEP を作成して割り当てるときにこれらの URI を使用する必要があるため、この情報を安全な場所に保存します。 このコマンドは、キーの読み取りごとに 1 回実行してください。
  
Azure PowerShell で、
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online および Skype for Business の顧客キーのセットアップ

始める前に、Azure Key Vault のセットアップに必要なタスクを完了していることを確認します。 詳細 [については、Azure Key Vault と Microsoft FastTrack のタスクの一覧](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
Exchange Online と Skype for Business のカスタマー キーをセットアップするには、Windows PowerShell と Exchange Online にリモート接続してこれらの手順を実行する必要があります。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online および Skype for Business で使用するためのデータ暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に保存されている一連のキーに関連付けられていいます。 Microsoft 365 のメールボックスに DEP を割り当てる。 次に、Microsoft 365 はポリシーで特定されたキーを使用してメールボックスを暗号化します。 DEP を作成するには、前の手順で取得した Key Vault URI が必要です。 手順 [については、「Azure Key Vault key」の URI の取得](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。
  
注意してください。 DEP を作成するときに、2 つの異なる Azure Key Vault に含む 2 つのキーを指定します。 これらのキーを地域冗長性を確実に確実にするために、これらのキーが 2 つの別個の Azure リージョンにあることを確認します。
  
DEP を作成するには、次の手順に従います。
  
1. ローカル コンピューターで、組織のグローバル管理者アクセス許可を持つ職場または学校のアカウントを使用して [、ローカル ウィンドウで Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) にWindows PowerShellします。

2. DEP を作成するには、次のコマンドを入力して New-DataEncryptionPolicy コマンドレットを使用します。

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   ここで、

   - *PolicyName* は、ポリシーに使用する名前です。 名前にスペースを含めることはできません。 たとえば、次の USA_mailboxes。

   - *ポリシーの説明* は、このポリシーの目的をわかりやすく説明するポリシーのわかりやすい説明です。 説明にはスペースを含めることが可能です。 たとえば、「USA とそのトリーフリストのルート キー」とします。

   - *KeyVaultURI1* は、ポリシーの最初のキーの URI です。 たとえば、<https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> などです。

   - *KeyVaultURI2 は* 、ポリシー内の 2 番目のキーの URI です。 たとえば、<https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> などです。 2 つの URI はカンマとスペースで区切ります。

   例:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

構文およびパラメーターの詳細については [、New-DataEncryptionPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)。

### <a name="assign-a-dep-to-a-mailbox"></a>DEP をメールボックスに割り当てる

Set-Mailbox コマンドレットを使用して、DEP をメールボックスに割り当て。 ポリシーを割り当てると、Microsoft 365 は DEP で指定されたキーを使ってメールボックスを暗号化できます。
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailboxIdParameter が*メールボックスを指定する場所。 Set-Mailbox コマンドレットの詳細については [、「Set-Mailbox」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。

iOS および Android 用の Outlook とハイブリッド先進認証で Outlook を使用する [オンプレミスのメールボックスの場合、Exchange](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)Online テナントに同期されるオンプレミスのメールボックス データに Set-MailUser コマンドレットを使用して DEP を割り当てできます。

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

*MailUserIdParameter は*メール ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。 Set-MailUser コマンドレットの詳細については [、「Set-MailUser」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)。
  
### <a name="validate-mailbox-encryption"></a>メールボックスの暗号化の検証

メールボックスの暗号化にはしらくらく時間がかかる場合があります。 ポリシーの割り当てが初めて実行される場合、サービスがメールボックスを暗号化する前に、メールボックスを 1 つのデータベースから別のデータベースに完全に移動する必要があります。 DEP を変更した後、または最初にメールボックスに DEP を割り当てる場合は、72 時間待ってから暗号化を検証できるようにしておくことをお勧めします。
  
Get-MailboxStatistics コマンドレットを使用して、メールボックスが暗号化されているかどうかを確認します。
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted プロパティは、メールボックスが暗号化されている場合 **は true** の値を返し、メールボックスが暗号化されていない **場合は false** の値を返します。

メールボックスの移動が完了する時間は、初めて DEP を割り当てたメールボックスの数と、メールボックスのサイズによって異なります。 DEP を割り当ててから 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーのセットアップ

始める前に、Azure Key Vault のセットアップに必要なタスクを完了していることを確認します。 詳細 [については、Azure Key Vault と Microsoft FastTrack のタスクの一覧](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) を参照してください。
  
SharePoint Online、OneDrive for Business、Teams の各ファイルのカスタマー キーをセットアップするには、これらの手順を実行する必要があります。これらの手順は、クラウドで SharePoint Online にリモート接続Windows PowerShell。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>SharePoint Online および OneDrive for Business の地域ごとにデータの暗号化ポリシー (DEP) を作成する

DEP は、Azure Key Vault に格納されているキーのセットに関連付けけれます。 GEO とも呼ばれる、1 つの地理的な場所にあるすべてのデータに DEP を適用します。 Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を持つ、geo ごとに 1 つの DEP を作成できます。 複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams のファイルと連用する DEP を組織内に 1 つ作成できます。 Microsoft 365 は DEP で特定されたキーを使用して、その geo でデータを暗号化します。 DEP を作成するには、前の手順で取得した Key Vault URI が必要です。 手順 [については、「Azure Key Vault key」の URI の取得](#obtain-the-uri-for-each-azure-key-vault-key) を参照してください。
  
注意してください。 DEP を作成するときに、2 つの異なる Azure Key Vault に含む 2 つのキーを指定します。 これらのキーを地域冗長性を確実に確実にするために、これらのキーが 2 つの別個の Azure リージョンにあることを確認します。
  
DEP を作成するには、リモートから次のコマンドを使用して SharePoint Online にリモート接続Windows PowerShell。
  
1. ローカル コンピューターで、組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを [使用して、SharePoint Online Powershell に接続します](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)。

2. Microsoft SharePoint Online 管理シェルで、Register-SPODataEncryptionPolicy コマンドレットを次のように実行します。

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   DEP を登録すると、暗号化は geo 内のデータから開始されます。 この処理には時間がかかる場合があります。

### <a name="validate-file-encryption"></a>ファイルの暗号化の検証

 SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化を検証するには [、SharePoint Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)し、Get-SPODataEncryptionPolicy コマンドレットを使用してテナントの状態を確認します。 _State プロパティは_、顧客キーの暗号化**が有効で**、すべてのサイト内のすべてのファイルが暗号化されている場合に、登録された値を返します。 暗号化が進行中の場合は、サイトのどのパーセンテージが完了したかに関する情報が表示されます。

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [サービスの暗号化](office-365-service-encryption.md)
