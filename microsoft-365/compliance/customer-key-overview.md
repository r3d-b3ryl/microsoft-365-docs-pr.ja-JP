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
ms.openlocfilehash: 9ed4b523c77cf1fa80d23e8fbe5c93e938f222a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916889"
---
# <a name="service-encryption-with-customer-key"></a>カスタマー キーによるサービスの暗号化

Microsoft 365 では、BitLocker と分散キー マネージャー (DKM) を介して有効になっているベースラインのボリューム レベルの暗号化が提供されます。 Microsoft 365 では、コンテンツのアプリケーション層に暗号化の層が追加されています。 このコンテンツには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルのデータが含まれます。 この追加された暗号化層は、サービス暗号化と呼ばれる。

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>サービスの暗号化、BitLocker、および顧客キーの機能

サービスの暗号化により、保存中のコンテンツがサービス層で暗号化されます。 **BitLocker と DKM を使用した Microsoft 365** サービスでは、データは常に保存時に暗号化されます。 詳細については、「セキュリティ、プライバシー、コンプライアンス情報」、および「Exchange Online が電子メール シークレットをセキュリティで保護する方法 [」を参照してください](exchange-online-secures-email-secrets.md)。 顧客キーは、承認されていないシステムまたは担当者によるデータの表示に対する追加の保護を提供し、Microsoft データセンターでの BitLocker ディスク暗号化を補完します。 サービスの暗号化は、Microsoft の担当者が顧客データにアクセスすることを妨げる意味ではありません。 主な目的は、ルート キーを制御するための規制またはコンプライアンスの義務を満たしているお客様を支援します。 お客様は、O365 サービスが暗号化キーを使用して、電子情報開示、マルウェア対策、スパム対策、検索インデックス作成などの付加価値クラウド サービスを提供するように明示的に承認します。

顧客キーはサービスの暗号化に基いて構築され、暗号化キーを提供および制御できます。 次に、Microsoft 365 は、オンライン サービス条項 (OST) の説明に従って、これらのキーを使用して保存中のデータ [を暗号化します](https://www.microsoft.com/licensing/product-licensing/products.aspx)。 顧客キーは、Microsoft 365 がデータの暗号化と復号化に使用する暗号化キーを制御するために、コンプライアンスの義務を満たすのに役立ちます。
  
顧客キーは、クラウド サービス プロバイダーとの重要な取り決めを指定するコンプライアンス要件の要求を満たす組織の機能を強化します。 顧客キーを使用すると、アプリケーション レベルで保存されている Microsoft 365 データのルート暗号化キーを提供および制御できます。 その結果、組織のキーを制御できます。 サービスを終了する場合は、組織のルート キーへのアクセスを取り消します。 すべての Microsoft 365 サービスでは、キーへのアクセスを取り消すのが、データ削除へのパスの最初のステップです。 キーへのアクセスを取りやめ、データはサービスに対して読み取り不能になります。

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>顧客キーは、365 で保存中のデータOfficeします。

指定したキーを使用して、顧客キーは次の暗号化を行います。

- SharePoint Online、OneDrive for Business、Teams ファイル。
- OneDrive for Business にアップロードされたファイル。
- 電子メール本文コンテンツ、予定表エントリ、電子メール添付ファイル内のコンテンツを含む Exchange Online メールボックスのコンテンツ。
- Skype for Business からのテキスト会話。

現在、Skype 会議ブロードキャストおよび Skype 会議コンテンツアップロードの暗号化キーの顧客制御は提供しません。 代わりに、このコンテンツは、365 の他のすべてのコンテンツOfficeされます。

### <a name="customer-key-with-hybrid-deployments"></a>ハイブリッド展開を使用したカスタマー キー

顧客キーは、クラウドで保存されているデータのみを暗号化します。 顧客キーは、オンプレミスのメールボックスとファイルを保護するために機能しません。 BitLocker などの別の方法を使用して、オンプレミスのデータを暗号化できます。

## <a name="about-the-data-encryption-policy-dep"></a>データ暗号化ポリシー (DEP) について

データ暗号化ポリシーは、提供する各キーと Microsoft によって保護された可用性キーを使用してデータを暗号化する暗号化階層を定義します。 サービスごとに異なる PowerShell コマンドレットを使用して DEP を作成し、それらの DEP を割り当て、アプリケーション データを暗号化します。 次に例を示します。

**Exchange Online と Skype for Business** テナントごとに最大 50 の DEP を作成できます。 DEP を Azure Key Vault の顧客キーに関連付け、個々のメールボックスに DEP を割り当てる。 メールボックスに DEP を割り当てる場合:

- メールボックスは、メールボックスの移動のマークが付いている。 ここで説明する Microsoft 365 の優先度に基づいて [、Microsoft 365](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)サービスで要求を移動します。

- 暗号化は、メールボックスの移動中に行います。 メールボックスが新しい DEP で暗号化されるのに 72 時間かかります。 DEP を割り当てた時刻から 72 時間待った後にメールボックスが暗号化されない場合は、Microsoft にお問い合わせください。

後で、「365 の顧客キーの管理」の説明に従って、DEP を更新するか、別の DEP [をメールボックスに割り](customer-key-manage.md)当Officeできます。 DEP を割り当てるには、各メールボックスに適切なライセンスが必要です。 ライセンスの詳細については、「顧客キーを設定 [する前に」を参照してください](customer-key-set-up.md#before-you-set-up-customer-key)。

> [!NOTE]
> DEP は、ユーザー メールボックスのライセンス要件を満たすテナントの共有メールボックス、パブリック フォルダー メールボックス、および Microsoft 365 グループ メールボックスに適用できます。これらのメールボックスの種類の一部は、割り当てられたライセンス (パブリック フォルダー メールボックスと Microsoft 365 グループ メールボックス) にできない場合や、記憶域 (共有メールボックス) を増やすライセンスが必要な場合でもです。

**SharePoint Online、OneDrive for Business、Teams ファイル** 複数地域機能を使用している場合は、組織の地域ごとに最大 1 つの DEP を作成できます。 地域ごとに異なる顧客キーを使用できます。 複数地域機能を使用していない場合は、テナントごとに 1 つの DEP のみを作成できます。 DEP を割り当てると、暗号化は自動的に開始されますが、完了に時間がかかる場合があります。 「顧客キーの設定 [」の詳細を参照してください](customer-key-set-up.md)。

## <a name="leaving-the-service"></a>サービスを離れる

顧客キーは、Microsoft 365 サービスを離れる際にキーを取り消し、コンプライアンスの義務を満たします。 サービスを離れる際にキーを取り消すと、可用性キーが削除され、データの暗号化が削除されます。 暗号化の削除は、セキュリティとコンプライアンスの両方の義務を満たす上で重要なデータの再管理のリスクを軽減します。 データ削除プロセスとキー失効の詳細については、「キーを取り消して、データ削除パス プロセス [を開始する」を参照してください](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)。

### <a name="encryption-ciphers-used-by-customer-key"></a>顧客キーで使用される暗号化暗号

顧客キーは、次の図に示すように、さまざまな暗号化暗号を使用してキーを暗号化します。

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business のキーを暗号化するために使用される暗号化暗号

![Exchange Online カスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのキーを暗号化するために使用される暗号化暗号

![SharePoint Online カスタマー キーの暗号化暗号](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>関連記事

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [カスタマー キーまたは可用性キーをローリングまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)

- [カスタマー ロックボックス](customer-lockbox-requests.md)

- [サービスの暗号化](office-365-service-encryption.md)