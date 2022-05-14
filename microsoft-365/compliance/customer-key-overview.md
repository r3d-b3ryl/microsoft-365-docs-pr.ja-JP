---
title: Microsoft Purview カスタマー キーを使用したサービスの暗号化
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: この記事では、サービス暗号化がMicrosoft Purviewカスタマー キーでどのように機能するかについて説明します。
ms.openlocfilehash: 3a0533b94cb70c9fc46d6246e99d3f9fdb5eb6e6
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415087"
---
# <a name="service-encryption-with-microsoft-purview-customer-key"></a>Microsoft Purview カスタマー キーを使用したサービスの暗号化

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft 365では、BitLocker と分散キー マネージャー (DKM) を使用して、ベースラインのボリューム レベルの暗号化が有効になります。 Microsoft 365では、コンテンツの暗号化レイヤーが追加されます。 このコンテンツには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Microsoft Teamsからのデータが含まれます。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>サービスの暗号化、BitLocker、カスタマー キーの連携方法

データは、BitLocker と DKM を使用してMicrosoft 365 サービスで保存時に常に暗号化されます。 詳細については、「Exchange Onlineが[電子メール シークレットをセキュリティで保護する方法」を参照してください](exchange-online-secures-email-secrets.md)。 カスタマー キーは、承認されていないシステムや個人によるデータの閲覧を防止するための追加の保護を提供し、Microsoft データセンターの Bitlocker ディスク暗号化を補完します。 サービスの暗号化は、Microsoft 担当者がデータにアクセスできないようにするためのものではありません。 代わりに、カスタマー キーは、ルート キーを制御するための規制またはコンプライアンスの義務を満たすのに役立ちます。 暗号化キーを使用して、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成など、付加価値の高いクラウド サービスを提供するために、Microsoft 365 サービスを明示的に承認します。

カスタマー キーはサービスの暗号化に基づいて構築されており、暗号化キーを提供および制御できます。 Microsoft 365これらのキーを使用して、[Online Services Terms (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) の説明に従って保存データを暗号化します。 カスタマー キーは、データの暗号化と暗号化解除にMicrosoft 365使用する暗号化キーを制御するため、コンプライアンスの義務を満たすのに役立ちます。
  
Customer Key は、クラウド サービス プロバイダーとの主要な取り決めを指定するコンプライアンス要件の要求を満たす組織の機能を強化します。 Customer Key を使用すると、Microsoft 365 データの保存時のルート暗号化キーをアプリケーション レベルで指定および制御できます。 その結果、組織のキーを制御できます。

## <a name="customer-key-with-hybrid-deployments"></a>ハイブリッド展開を使用したカスタマー キー

Customer Key では、クラウド内の保存データのみが暗号化されます。 顧客キーは、オンプレミスのメールボックスとファイルを保護するために機能しません。 BitLocker などの別の方法を使用して、オンプレミスデータを暗号化できます。

## <a name="about-data-encryption-policies"></a>データ暗号化ポリシーについて

データ暗号化ポリシー (DEP) は、暗号化階層を定義します。 この階層は、管理する各キーと Microsoft によって保護されている可用性キーを使用してデータを暗号化するためにサービスによって使用されます。 PowerShell コマンドレットを使用して DEP を作成し、それらの DEP を割り当ててアプリケーション データを暗号化します。 カスタマー キーでサポートされている DEP には 3 種類あり、ポリシーの種類ごとに異なるコマンドレットが使用され、異なる種類のデータに対するカバレッジが提供されます。 定義できる DEP は次のとおりです。

**複数のMicrosoft 365 ワークロードの DEP** これらの DEP は、テナント内のすべてのユーザーに対して複数の M365 ワークロード間でデータを暗号化します。 これらのワークロードには、次のものが含まれます。

- Teams チャット メッセージ (1 対 1 のチャット、グループ チャット、会議チャット、チャネル会話)
- Teams メディア メッセージ (画像、コード スニペット、ビデオ メッセージ、オーディオ メッセージ、Wiki 画像)
- Teams ストレージに保存された通話と会議の録音をTeamsする
- チャット通知をTeamsする
- Cortanaによるチャットの提案をTeamsする
- 状態メッセージをTeamsする
- Exchange Onlineのユーザーとシグナルの情報
- メールボックス DEP によってまだ暗号化されていないメールボックスをExchange Onlineする
- 統合監査ログ ストレージ
- Microsoft Purview 情報保護:

  - データ ファイル スキーマ、ルール パッケージ、機密データのハッシュに使用される塩分を含む、完全なデータ一致 (EDM) データ。 EDM とMicrosoft Teamsの場合、マルチワークロード DEP は、DEP をテナントに割り当てた時点から新しいデータを暗号化します。 Exchange Onlineの場合、Customer Key は既存のデータと新しいデータをすべて暗号化します。

  - 秘密度ラベルのラベル構成

マルチワークロード DEP では、次の種類のデータは暗号化されません。 代わりに、Microsoft 365はこのデータを保護するために他の種類の暗号化を使用します。

- データのSharePointとOneDrive for Business。
- Microsoft Teams ファイルと、OneDrive for BusinessおよびSharePoint Online に保存された一部のTeams通話と会議の記録は、SharePoint Online DEP を使用して暗号化されます。
- カスタマー キーで現在サポートされていないYammerや Planner などの他のMicrosoft 365 ワークロード。
- ライブ イベント データをTeamsします。

テナントごとに複数の DEP を作成できますが、一度に割り当てられる DEP は 1 つだけです。 DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズに応じて完了するまでに時間がかかります。

**Exchange Online メールボックスの DEP** メールボックス DEP を使用すると、Exchange Online内の個々のメールボックスをより正確に制御できます。 メールボックス DEP を使用して、UserMailbox、MailUser、Group、PublicFolder、共有メールボックスなど、さまざまな種類の EXO メールボックスに格納されているデータを暗号化します。 テナントごとに最大 50 個のアクティブ DEP を持ち、それらの DEP を個々のメールボックスに割り当てることができます。 1 つの DEP を複数のメールボックスに割り当てることができます。

既定では、メールボックスは Microsoft マネージド キーを使用して暗号化されます。 顧客キー DEP をメールボックスに割り当てる場合:

- マルチワークロード DEP を使用してメールボックスが暗号化されている場合、ユーザーまたはシステム操作がメールボックス データにアクセスする限り、サービスは新しいメールボックス DEP を使用してメールボックスを再ラップします。

- Microsoft マネージド キーを使用してメールボックスが既に暗号化されている場合、ユーザーまたはシステム操作がメールボックス データにアクセスする限り、サービスは新しいメールボックス DEP を使用してメールボックスを再ラップします。

- 既定の暗号化を使用してメールボックスがまだ暗号化されていない場合、サービスはメールボックスに移動のマークを付けます。 暗号化は、移動が完了すると行われます。 メールボックスの移動は、すべてのMicrosoft 365に設定された優先順位に基づいて管理されます。 詳細については、「[Microsoft 365 サービスで要求を移動する」を](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-microsoft-365-or-office-365-service)参照してください。 指定した時間内にメールボックスが暗号化されない場合は、Microsoft にお問い合わせください。

後で、DEP を更新するか、別の DEP をメールボックスに割り当てることができます。「[Office 365のカスタマー キーの管理](customer-key-manage.md)」の説明に従います。 各メールボックスには、DEP を割り当てる適切なライセンスが必要です。 ライセンスの詳細については、「 [カスタマー キーを設定する前に](customer-key-set-up.md#before-you-set-up-customer-key)」を参照してください。

DEP は、ユーザー メールボックスのライセンス要件を満たすテナントの共有メールボックス、パブリック フォルダー メールボックス、Microsoft 365 グループ メールボックスに割り当てることができます。 Customer Key DEP を割り当てるには、ユーザー固有以外のメールボックスに個別のライセンスは必要ありません。

個々のメールボックスに割り当てる Customer Key DEP の場合は、サービスを終了するときに Microsoft に特定の DEP を消去するように要求できます。 データ消去プロセスとキー失効の詳細については、「 [キーを取り消してデータ消去パス プロセスを開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

サービスを終了する一環としてキーへのアクセスを取り消すと、可用性キーが削除され、データの暗号化が削除されます。 暗号化の削除は、セキュリティとコンプライアンスの両方の義務を満たす上で重要なデータの復旧のリスクを軽減します。

**SHAREPOINT Online および OneDrive for Business の DEP** この DEP は、SPO に格納されているMicrosoft Teams ファイルを含む、SPO およびOneDrive for Businessに格納されているコンテンツを暗号化するために使用されます。 複数地域機能を使用している場合は、組織の geo ごとに 1 つの DEP を作成できます。 複数地域機能を使用していない場合は、テナントごとに 1 つの DEP のみを作成できます。 [カスタマー キーの設定に関](customer-key-set-up.md)する詳細を参照してください。

### <a name="encryption-ciphers-used-by-customer-key"></a>Customer Key で使用される暗号化暗号

カスタマー キーでは、次の図に示すように、さまざまな暗号化暗号を使用してキーを暗号化します。

複数のMicrosoft 365 ワークロードのデータを暗号化する DEP に使用されるキー階層は、個々のExchange Online メールボックスの DEP に使用される階層に似ています。 唯一の違いは、メールボックス キーが対応するMicrosoft 365ワークロード キーに置き換えられている点です。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange OnlineとSkype for Businessのキーを暗号化するために使用される暗号化暗号

![Exchange Onlineカスタマー キーの暗号化暗号。](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのキーを暗号化するために使用される暗号化暗号

![SharePoint Online カスタマー キーの暗号化暗号。](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [カスタマー キーを設定する](customer-key-set-up.md)

- [カスタマー キーを管理する](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービス暗号化](office-365-service-encryption.md)
