---
title: サービスの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: データの復元性についてMicrosoft Office 365。'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216693"
---
# <a name="service-encryption"></a>サービスの暗号化

ボリューム レベルの暗号化の使用に加えて、Exchange Online、Microsoft Teams、SharePoint Online、および OneDrive for Business サービス暗号化を使用して顧客データを暗号化します。 サービスの暗号化では、次の 2 つのキー管理オプションを使用できます。

## <a name="microsoft-managed-keys"></a>Microsoft が管理するキー
Microsoft は、サービス暗号化のルート キーを含むすべての暗号化キーを管理します。 このオプションは現在、オンライン、オンライン、Exchange Online、SharePointに対してOneDrive for Business。 Microsoft 管理キーは、顧客キーを使用してオンボードを決定しない限り、既定のサービス暗号化を提供します。 後日、データ削除パスに従わずに顧客キーの使用を停止する場合、データは Microsoft 管理キーを使用して暗号化されたままです。 データは、少なくともこの既定のレベルで常に暗号化されます。 

## <a name="customer-key"></a>顧客キー
サービス暗号化で使用されるルート キーを指定し、Azure Key Vault を使用してこれらのキーを管理します。 Microsoft は、他のすべてのキーを管理します。 このオプションは Customer Key と呼ばされ、現在、オンライン、Exchange Online、SharePoint、およびOneDrive for Business。 (以前は BYOK による高度な暗号化と呼ばば) 元[のアナウンスについては、「ユーザーの透明性とコントロールOffice 365強化](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)する」を参照してください。

サービスの暗号化には、次の複数の利点があります。

- BitLocker の上に追加の保護層を提供します。

- オペレーティング システム管理者Windows、オペレーティング システムによって保存または処理されるアプリケーション データへのアクセスから分離します。

- テナントごとのキー管理を提供するマルチテナント サービスを有効にする顧客キー オプションが含まれています。

- 暗号化に関する特定のMicrosoft 365を持つ顧客の要求を満たす機能を強化します。

顧客キーを使用すると、オンプレミスのハードウェア サービス モジュール (HSM) または Azure Key Vault (AKV) のいずれかを使用して、独自の暗号化キーを生成できます。 キーの生成方法に関係なく、AKV を使用して、ユーザーが使用する暗号化キーを制御および管理Office 365。 キーを AKV に格納すると、メールボックス データまたはファイルを暗号化するキーチェーンのルートとして使用できます。

顧客キーのもう 1 つの利点は、Microsoft がデータを処理する機能を制御することです。 microsoft でサービスを終了する場合や、クラウドに保存されているデータの一部を削除する場合など、Office 365 からデータを削除する場合は、テクニカル コントロールとしてカスタマー キーを使用できます。 データを削除すると、Microsoft を含む誰もデータにアクセスまたは処理できます。 顧客キーは、Microsoft 担当者によるデータへのアクセスを制御するために使用する顧客ロックボックスに加えて補完的です。

Microsoft 365、Microsoft Teams、SharePoint Exchange Online Online (チーム サイト、OneDrive for Business など) の顧客キーを設定する方法については、次の記事を参照してください。

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [顧客キーまたは可用性キーをロールまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーについて](customer-key-availability-key-understand.md)
