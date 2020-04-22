---
title: 顧客キーによるサービスの暗号化
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
description: 顧客キーを使用して、組織の暗号化キーを制御し、microsoft 365 を使用して Microsoft のデータセンターで保存されているデータを暗号化するように構成します。
ms.openlocfilehash: 701dc306a81e12db7dd1062d2a840621b710abd3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635593"
---
# <a name="service-encryption-with-customer-key"></a>顧客キーによるサービスの暗号化

Microsoft 365 では、BitLocker および Distributed Key Manager (DKM) によって有効になる、ベースライン、ボリュームレベルの暗号化が提供されています。 Microsoft 365 は、コンテンツのためにアプリケーションレベルで暗号化の層を追加しています。 このコンテンツには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams の各ファイルからのデータが含まれています。 この追加の暗号化層は、サービス暗号化と呼ばれます。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>サービス暗号化、BitLocker、および顧客キーがどのように連携するか

サービス暗号化によって、rest のコンテンツはアプリケーションレイヤーで暗号化されます。 **データは常に、BitLocker および DKM を使用して、Microsoft 365 サービスで常に暗号化され**ます。 詳細については、「セキュリティ、プライバシー、コンプライアンスに関する情報」、および「 [Exchange Online で電子メールの機密を保護する方法](exchange-online-secures-email-secrets.md)」を参照してください。 顧客キーは、承認されていないシステムまたは個人によるデータの表示に対する追加の保護を提供し、Microsoft データセンターの BitLocker ディスク暗号化を補完します。 サービス暗号化は、Microsoft の担当者が顧客データにアクセスできないようにすることを意図したものではありません。 主な目的は、お客様がルートキーを制御するための規制または法令遵守義務をサポートすることです。 お客様は、暗号化キーを使用して、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成などの付加価値のあるクラウドサービスを提供するために、O365 サービスを明示的に承認します。

顧客キーはサービス暗号化に基づいて構築されており、暗号化キーを提供および制御できます。 Microsoft 365 は、これらのキーを使用して、[オンラインサービス用語 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)で説明されているように、保存したデータを暗号化します。 顧客キーは、Microsoft 365 がデータを暗号化および復号化する際に使用する暗号化キーを制御するため、コンプライアンスの義務を満たすのに役立つ。
  
顧客キーは、クラウドサービスプロバイダーとの主要な手配を指定するコンプライアンス要件を満たすための組織の能力を向上させます。 Customer キーを使用すると、Microsoft 365 データ保存用のルート暗号化キーをアプリケーションレベルで提供および制御できます。 そのため、組織のキーを制御します。 サービスを終了することを決定した場合は、組織のルートキーへのアクセスを取り消します。 Microsoft 365 のすべてのサービスについて、キーへのアクセスを取り消すことが、データ削除へのパスの最初の手順です。 キーへのアクセスを取り消すことにより、データはサービスから読み取ることができなくなります。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>顧客キーが Office 365 で保存されるデータを暗号化する

指定したキーを使用すると、顧客キーが暗号化を行います。

- SharePoint Online、OneDrive for Business、および Teams ファイル。
- OneDrive for business にアップロードされたファイル。
- 電子メールの本文のコンテンツ、予定表のエントリ、電子メールの添付ファイル内のコンテンツなどの Exchange Online メールボックスのコンテンツ。
- Skype for Business からのテキスト会話。

現時点では、Skype 会議ブロードキャストと Skype 会議コンテンツのアップロードの暗号化キーのカスタマーコントロールは提供していません。 代わりに、このコンテンツは Office 365 の他のすべてのコンテンツと共に暗号化されます。

### <a name="customer-key-with-hybrid-deployments"></a>ハイブリッド展開での顧客キー

顧客キーは、クラウドで保存されているデータのみを暗号化します。 顧客キーは、社内のメールボックスやファイルを保護するためには機能しません。 他の方法 (BitLocker など) を使用してオンプレミスのデータを暗号化することができます。

## <a name="about-the-data-encryption-policy-dep"></a>データ暗号化ポリシーについて (DEP)

データ暗号化ポリシーは、提供するキーと、Microsoft によって保護された可用性キーを使用して、データを暗号化するための暗号化階層を定義します。 サービスごとに異なる PowerShell コマンドレットを使用して DEPs を作成し、アプリケーションデータを暗号化するように DEPs を割り当てます。 以下に例を示します。

**Exchange Online と Skype For business**テナントごとに最大 50 DEPs を作成できます。 Azure Key Vault で DEPs を顧客キーに関連付け、DEPs を個々のメールボックスに割り当てます。 メールボックスに DEP を割り当てると、次のようになります。

- メールボックスは、メールボックスの移動のためにマークされます。 Microsoft 365 の優先度に基づいて[、「microsoft 365 サービスでの移動要求](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)」を参照してください。

- 暗号化は、メールボックスが移動されている間に行われます。 メールボックスが新しい DEP で暗号化されるように72時間を許可します。 DEP を割り当てた時点から72時間が経過した後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。

後で、DEP を最新の情報に更新するか、「 [Office 用の顧客キーの管理 365](customer-key-manage.md)」で説明されているように、別の dep をメールボックスに割り当てます。 各メールボックスは、DEP を割り当てるために適切なライセンスを持っている必要があります。 ライセンスの詳細については、「[顧客キーを設定する前に](customer-key-set-up.md#before-you-set-up-customer-key)」を参照してください。

**SharePoint Online、OneDrive For business、Teams ファイル**複数地域機能を使用している場合は、組織の各 geo に対して最大1つの DEP を作成できます。 地域ごとに異なる顧客キーを使用できます。 複数地域機能を使用していない場合は、テナントごとに1つの DEP のみを作成できます。 DEP を割り当てた場合、暗号化は自動的に開始されますが、完了するまでしばらく時間がかかる場合があります。 「 [Set Up Customer Key](customer-key-set-up.md)」の詳細を参照してください。

## <a name="leaving-the-service"></a>サービスからの脱退

顧客キーは、Microsoft 365 サービスを終了する際にキーを失効させることで、コンプライアンスの義務を満たすために役立ちます。 サービスを終了する際にキーを無効にすると、可用性キーが削除され、データの暗号化削除が発生します。 暗号化の削除は、セキュリティとコンプライアンスの両方の義務を満たすことが重要なデータ再構築のリスクを軽減します。 データ削除プロセスとキーの失効の詳細については、「[キーを失効化し、データ削除パスの処理を開始する](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)」を参照してください。

### <a name="encryption-ciphers-used-by-customer-key"></a>顧客キーで使用される暗号化暗号

顧客キーは、次の図に示すように、さまざまな暗号化暗号を使用してキーを暗号化します。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のキーを暗号化するために使用される暗号化暗号

![Exchange Online の顧客キーの暗号化暗号](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのキーを暗号化するために使用される暗号化暗号

![SharePoint Online の顧客キーの暗号化暗号](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [顧客キーを設定する](customer-key-set-up.md)

- [顧客キーを管理する](customer-key-manage.md)

- [顧客キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーについて](customer-key-availability-key-understand.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービス暗号化](office-365-service-encryption.md)
