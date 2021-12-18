---
title: カスタマー キーによるサービスの暗号化
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
description: この記事では、サービスの暗号化が顧客キーとどのように機能するのかについてMicrosoft 365。
ms.openlocfilehash: 7e81c6eb7e6ce6f7ac2ea2f8a61f15084032e955
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560170"
---
# <a name="service-encryption-with-customer-key"></a>カスタマー キーによるサービスの暗号化

Microsoft 365、BitLocker と分散キー マネージャー (DKM) を使用して有効になっているベースラインのボリューム レベルの暗号化を提供します。 Microsoft 365コンテンツの暗号化レイヤーが追加されています。 このコンテンツには、オンライン、Exchange Online、Skype for Business、SharePoint、OneDrive for Business、およびMicrosoft Teams。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>サービスの暗号化、BitLocker、および顧客キーの機能

BitLocker と DKM を使用して、Microsoft 365サービスでデータは常に暗号化されます。 詳細については、「メール シークレット[をセキュリティで保護Exchange Online方法」を参照してください](exchange-online-secures-email-secrets.md)。 顧客キーは、承認されていないシステムまたは担当者によるデータの表示に対する追加の保護を提供し、Microsoft データ センターでの BitLocker ディスク暗号化を補完します。 サービスの暗号化は、Microsoft の担当者がデータにアクセスすることを妨げる意味ではありません。 代わりに、顧客キーは、ルート キーを制御するための規制またはコンプライアンスの義務を満たすのに役立ちます。 Microsoft 365 サービスに対して、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成などの付加価値クラウド サービスを提供するために、暗号化キーを使用するように明示的に承認します。

顧客キーはサービスの暗号化に基いて構築され、暗号化キーを提供および制御できます。 Microsoft 365これらのキーを使用して、オンライン サービス条項 (OST) の説明に従って保存時のデータ[を暗号化します](https://www.microsoft.com/licensing/product-licensing/products.aspx)。 顧客キーは、データの暗号化と暗号化解除に使用する暗号化Microsoft 365を制御するために、コンプライアンスの義務を満たすのに役立ちます。
  
顧客キーは、クラウド サービス プロバイダーとの重要な取り決めを指定するコンプライアンス要件の要求を満たす組織の機能を強化します。 顧客キーを使用すると、アプリケーション レベルでデータを保存Microsoft 365のルート暗号化キーを提供および制御できます。 その結果、組織のキーを制御できます。

## <a name="customer-key-with-hybrid-deployments"></a>ハイブリッド展開を使用したカスタマー キー

顧客キーは、クラウドで保存されているデータのみを暗号化します。 顧客キーは、オンプレミスのメールボックスとファイルを保護するために機能しません。 BitLocker などの別の方法を使用して、オンプレミスのデータを暗号化できます。

## <a name="about-data-encryption-policies"></a>データ暗号化ポリシーについて

データ暗号化ポリシー (DEP) は、暗号化階層を定義します。 この階層は、管理する各キーと Microsoft によって保護されている可用性キーを使用してデータを暗号化するためにサービスによって使用されます。 PowerShell コマンドレットを使用して DEP を作成し、それらの DEP を割り当て、アプリケーション データを暗号化します。 Microsoft 365 Customer Key でサポートされる DEP には 3 種類があります。各ポリシーの種類は異なるコマンドレットを使用し、さまざまな種類のデータに対応します。 定義できる DEP は次のとおりです。

**複数のユーザーのワークロードMicrosoft 365 DEP** これらの DEP は、テナント内のすべてのユーザーに対して複数の M365 ワークロードにわたってデータを暗号化します。 これらのワークロードには、次のものが含まれます。

- Teamsチャット メッセージ (1:1 チャット、グループ チャット、会議チャット、チャネル会話)
- Teamsメディア メッセージ (画像、コード スニペット、ビデオ メッセージ、オーディオ メッセージ、Wiki イメージ)
- Teamsストレージに保存されている通話と会議のTeams記録
- Teamsチャット通知
- Teamsによるチャットの提案Cortana
- Teams状態メッセージ
- ユーザーとシグナルの情報をExchange Online
- Exchange Online DEP によってまだ暗号化されていないメールボックス
- Microsoft Information Protection:

  - データ ファイル スキーマ、ルール パッケージ、機密データのハッシュに使用される塩を含む、完全なデータ一致 (EDM) データ。 EDM および Microsoft Teams、マルチワークロード DEP は、DEP をテナントに割り当てる時から新しいデータを暗号化します。 たとえばExchange Online、顧客キーは既存のデータと新しいデータを暗号化します。

  - 感度ラベルのラベル構成

複数ワークロード DEP は、次の種類のデータを暗号化しない。 代わりに、Microsoft 365他の種類の暗号化を使用してこのデータを保護します。

- SharePointおよびOneDrive for Businessデータ。
- Microsoft Teams および Teams および OneDrive for Business SharePoint Online に保存されている一部の通話および会議の録音は、SharePoint オンライン DEP を使用して暗号化されます。
- 顧客Microsoft 365サポートされていないYammerプランナーなどの他のワークロード。
- Teamsライブ イベント データを取得します。

テナントごとに複数の DEP を作成できますが、一度に割り当てる DEP は 1 つのみです。 DEP を割り当てると、暗号化は自動的に開始されますが、テナントのサイズに応じて完了に時間がかかっています。

**メールボックスの DEP Exchange Online** メールボックス DEP は、メールボックス内の個々のメールボックスをExchange Online。 メールボックス DEP を使用して、UserMailbox、MailUser、Group、PublicFolder、共有メールボックスなど、さまざまな種類の EXO メールボックスに格納されているデータを暗号化します。 テナントごとに最大 50 個のアクティブ DEP を持ち、それらの DEP を個々のメールボックスに割り当てできます。 1 つの DEP を複数のメールボックスに割り当てできます。

既定では、メールボックスは Microsoft 管理キーを使用して暗号化されます。 顧客キー DEP をメールボックスに割り当てる場合:

- 複数ワークロードの DEP を使用してメールボックスが暗号化されている場合、ユーザーまたはシステム操作がメールボックス データにアクセスする限り、サービスは新しいメールボックス DEP を使用してメールボックスを再ラップします。

- Microsoft で管理されたキーを使用してメールボックスが既に暗号化されている場合、ユーザーまたはシステム操作がメールボックス データにアクセスする限り、サービスは新しいメールボックス DEP を使用してメールボックスを再ラップします。

- 既定の暗号化を使用してメールボックスがまだ暗号化されていない場合、サービスはメールボックスに移動のマークを付けします。 暗号化は、移動が完了すると行います。 メールボックスの移動は、すべてのユーザーに設定された優先度に基づいてMicrosoft 365。 詳細については、「Move requests in [the Microsoft 365 サービス」を参照してください](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-microsoft-365-or-office-365-service)。 指定した時間内にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

後で、DEP を更新するか、別の DEP をメールボックスに割り当てる (「顧客キーの管理」の説明に従って[Office 365。](customer-key-manage.md) 各メールボックスには、DEP を割り当てる適切なライセンスが必要です。 ライセンスの詳細については、「顧客キーを設定 [する前に」を参照してください](customer-key-set-up.md#before-you-set-up-customer-key)。

ユーザー メールボックスのライセンス要件を満たすテナントの共有メールボックス、パブリック フォルダー メールボックス、Microsoft 365 グループ メールボックスに DEP を割り当てることができます。 顧客キー DEP を割り当てるには、ユーザー固有以外のメールボックスに個別のライセンスは必要はありません。

個々のメールボックスに割り当てる顧客キー DEP の場合、サービスを離れるときに Microsoft に特定の DEP の削除を要求できます。 データ削除プロセスとキー失効の詳細については、「キーを取り消して、データ削除パス プロセス [を開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

サービスを離れる際にキーへのアクセスを取り消すと、可用性キーが削除され、データの暗号化が削除されます。 暗号化の削除は、データの再管理のリスクを軽減します。これは、セキュリティとコンプライアンスの両方の義務を満たす上で重要です。

**DEP for SharePoint Online** および OneDrive for Business この DEP は、SPO および OneDrive for Business に保存されているコンテンツ (SPO に保存されている Microsoft Teams ファイルを含む) を暗号化するために使用されます。 複数地域機能を使用している場合は、組織の地域ごとに 1 つの DEP を作成できます。 複数地域機能を使用していない場合は、テナントごとに 1 つの DEP のみを作成できます。 「顧客キーの設定 [」の詳細を参照してください](customer-key-set-up.md)。

### <a name="encryption-ciphers-used-by-customer-key"></a>顧客キーで使用される暗号化暗号

顧客キーは、次の図に示すように、さまざまな暗号化暗号を使用してキーを暗号化します。

複数のワークロードのデータを暗号化する DEP に使用Microsoft 365キー階層は、個々のメールボックスの DEP に使用される階層Exchange Online似ています。 唯一の違いは、メールボックス キーが対応するワークロード キーに置き換Microsoft 365です。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>暗号化と暗号化のキーを暗号化するためにExchange Online暗号化Skype for Business

![顧客キーの暗号化Exchange Online暗号化。](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Online、SharePoint、およびファイルのOneDrive for Business暗号化にTeams暗号化

![オンライン顧客キー SharePoint暗号化暗号。](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービスの暗号化](office-365-service-encryption.md)
