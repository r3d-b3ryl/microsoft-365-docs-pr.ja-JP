---
title: カスタマー キーによるサービスの暗号化
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: この記事では、Microsoft 365 の顧客キーでサービスの暗号化がどのように機能するのかについて説明します。
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058490"
---
# <a name="service-encryption-with-customer-key"></a>カスタマー キーによるサービスの暗号化

Microsoft 365 は、BitLocker と Distributed Key Manager (DKM) を通じて有効にされたベースラインのボリューム レベルの暗号化を提供します。 Microsoft 365 は、コンテンツのアプリケーション レイヤーで暗号化のレイヤーを追加します。 このコンテンツには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルのデータが含まれます。 この暗号化の追加レイヤーをサービス暗号化と呼ぶ。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>サービスの暗号化、BitLocker、および顧客キーの機能

サービスの暗号化により、保存中のコンテンツがサービス層で暗号化されます。 **データは常に BitLocker** と DKM を使用して Microsoft 365 サービスで暗号化されます。 詳細については、「セキュリティ、プライバシー、およびコンプライアンス情報」を参照してください。また、Exchange Online が電子メール シークレットをセキュリティで保護する [方法を参照してください](exchange-online-secures-email-secrets.md)。 顧客キーは、承認されていないシステムまたは担当者によるデータの表示に対する追加の保護を提供し、Microsoft データセンターでの BitLocker ディスク暗号化を補完します。 サービスの暗号化は、Microsoft の担当者が顧客データにアクセスすることを防ぐための機能ではありません。 主な目的は、ルート キーの制御に関する規制やコンプライアンスの義務を満たすお客様を支援する目的です。 お客様は、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成などの付加価値クラウド サービスを提供するために、暗号化キーを使用する O365 サービスを明示的に承認します。

顧客キーは、サービスの暗号化を基に構築され、暗号化キーを提供および制御できます。 Microsoft 365 は、オンライン サービスの使用条件 (OST) に記載されているとおり、これらのキーを使用して保存データ [を暗号化します](https://www.microsoft.com/licensing/product-licensing/products.aspx)。 顧客キーは、Microsoft 365 がデータの暗号化と暗号化解除に使用する暗号化キーを制御するために、コンプライアンスの義務を果たすのに役立ちます。
  
顧客キーは、クラウド サービス プロバイダーとの重要な取り決めを指定するコンプライアンス要件の要求を満たす組織の能力を強化します。 顧客キーを使用すると、Microsoft 365 データのルート暗号化キーをアプリケーション レベルで提供および制御できます。 その結果、組織のキーを制御できます。 サービスを終了する場合は、組織のルート キーへのアクセスを取り消します。 すべての Microsoft 365 サービスで、キーへのアクセスを取り消すのが、データ削除へのパスの最初の手順です。 キーへのアクセスを取り直すにより、データはサービスで読み取り不能になります。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>顧客キーは、365 年 1 月 365 日に保存Office暗号化します。

顧客キーは、入力したキーを使用して次の暗号化を行います。

- SharePoint Online、OneDrive for Business、および Teams ファイル。
- OneDrive for Business にアップロードされたファイル。
- 電子メール本文の内容、予定表のエントリ、電子メールの添付ファイル内のコンテンツを含む Exchange Online メールボックスのコンテンツ。
- Skype for Business からのテキスト会話。

現在、Skype 会議ブロードキャストと Skype 会議コンテンツのアップロードに関する暗号化キーの顧客制御は提供しません。 代わりに、このコンテンツは 365 年 1 月 365 日に他のすべてのコンテンツOfficeされます。

### <a name="customer-key-with-hybrid-deployments"></a>ハイブリッド展開での顧客キー

顧客キーは、クラウド内の保存データのみを暗号化します。 顧客キーは、オンプレミスのメールボックスとファイルの保護には機能しません。 BitLocker などの別の方法を使用して、オンプレミスのデータを暗号化できます。

## <a name="about-the-data-encryption-policy-dep"></a>データ暗号化ポリシー (DEP) について

データ暗号化ポリシーは、ユーザーが指定した各キーと Microsoft によって保護されている可用性キーを使用してデータを暗号化する暗号化階層を定義します。 サービスごとに異なる PowerShell コマンドレットを使用して DEP を作成し、それらの DEP を割り当て、アプリケーション データを暗号化します。 次に、例を示します。

**Exchange Online と Skype for Business** テナントごとに最大 50 の DEP を作成できます。 DEP を Azure Key Vault の顧客キーに関連付け、DEP を個々のメールボックスに割り当てる。 メールボックスに DEP を割り当てる場合:

- メールボックスはメールボックス移動のマークが付いている。 ここで説明する Microsoft 365 の優先事項に基づいて [、Microsoft 365](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)サービスで要求を移動します。

- 暗号化は、メールボックスの移動中に行います。 メールボックスが新しい DEP で暗号化されるのに 72 時間かかります。 DEP を割り当てた時間から 72 時間待った後にメールボックスが暗号化されない場合は、Microsoft にお問い合わせください。

後で、DEP を更新するか、「Office [365](customer-key-manage.md)の顧客キーの管理」の説明に従ってメールボックスに別の DEP を割り当てできます。 DEP を割り当てるには、各メールボックスに適切なライセンスが必要です。 ライセンスの詳細については、「顧客キーを設定 [する前に」を参照してください](customer-key-set-up.md#before-you-set-up-customer-key)。

> [!NOTE]
> DEP は、ユーザー メールボックスのライセンス要件を満たすテナントの共有メールボックス、パブリック フォルダー メールボックス、および Microsoft 365 グループ メールボックスに適用できます。一部の種類のメールボックスは、割り当てられたライセンス (パブリック フォルダー メールボックスと Microsoft 365 グループ メールボックス) にできない場合や、記憶域 (共有メールボックス) を増やすライセンスが必要な場合でも使用できます。

**SharePoint Online、OneDrive for Business、Teams ファイル** 複数地域機能を使用している場合は、組織の geo ごとに最大 1 つの DEP を作成できます。 geo ごとに異なるカスタマー キーを使用できます。 複数地域機能を使用していない場合は、テナントごとに 1 つの DEP のみを作成できます。 DEP を割り当てると、暗号化は自動的に開始されますが、完了まで時間がかかる場合があります。 「顧客キーのセットアップ [」の詳細を参照してください](customer-key-set-up.md)。

## <a name="leaving-the-service"></a>サービスを離れる

カスタマー キーは、Microsoft 365 サービスを離れる際にキーを取り消せという方法でコンプライアンスの義務を果たします。 サービスを離れる際にキーを取り消すと、可用性キーが削除され、データが暗号化によって削除されます。 暗号化削除は、セキュリティとコンプライアンスの両方の義務を果たす上で重要なデータの再管理のリスクを軽減します。 データの削除プロセスとキーの取り消しの詳細については、「キーを取り消し、データ消去パス プロセス [を開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

### <a name="encryption-ciphers-used-by-customer-key"></a>顧客キーで使用される暗号化暗号

顧客キーは、次の図に示すように、さまざまな暗号化暗号を使用してキーを暗号化します。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のキーを暗号化するために使用される暗号化暗号

![Exchange Online 顧客キーの暗号化暗号](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、および Teams ファイルのキーを暗号化するために使用される暗号化暗号

![SharePoint Online 顧客キーの暗号化暗号](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービスの暗号化](office-365-service-encryption.md)
