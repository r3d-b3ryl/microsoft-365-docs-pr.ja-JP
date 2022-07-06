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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365のデータ回復性について理解します。'
ms.openlocfilehash: 66899a337e9349a78178df67aa83e44b580c7148
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629381"
---
# <a name="service-encryption"></a>サービス暗号化

ボリューム レベルの暗号化を使用するだけでなく、Exchange Online、Microsoft Teams、SharePoint Online、OneDrive for Businessもサービス暗号化を使用して顧客データを暗号化します。 サービス暗号化では、次の 2 つのキー管理オプションを使用できます。

## <a name="microsoft-managed-keys"></a>Microsoft が管理するキー
Microsoft は、サービス暗号化のルート キーを含むすべての暗号化キーを管理します。 現在、このオプションは、Exchange Online、SharePoint Online、OneDrive for Businessで既定で有効になっています。 Microsoft マネージド キーは、カスタマー キーを使用してオンボードすることにした場合を除き、既定のサービス暗号化を提供します。 後日、データ消去パスに従わずにカスタマー キーの使用を停止することにした場合、データは Microsoft マネージド キーを使用して暗号化されたままになります。 データは、少なくともこの既定のレベルで常に暗号化されます。 

## <a name="customer-key"></a>顧客キー
サービス暗号化で使用されるルート キーを指定し、Azure Key Vaultを使用してこれらのキーを管理します。 Microsoft は他のすべてのキーを管理します。 このオプションは Customer Key と呼ばれ、現在はExchange Online、SharePoint Online、およびOneDrive for Businessで使用できます。 (以前は BYOK を使用した高度な暗号化と呼ばれた。 「元のお知らせ[のOffice 365顧客の透明性と制御の強化](https://www.microsoft.com/en-us/microsoft-365/blog/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)」を参照してください)。

サービス暗号化には、次の複数の利点があります。

- BitLocker の上に保護レイヤーを追加します。

- Windows オペレーティング システム管理者を、オペレーティング システムによって格納または処理されたアプリケーション データへのアクセスから分離します。

- マルチテナント サービスがテナントごとのキー管理を提供できるようにする Customer Key オプションが含まれています。

- 暗号化に関する特定のコンプライアンス要件を持つ顧客の要求を満たす Microsoft 365 の機能を強化します。

Customer Key を使用すると、オンプレミスのハードウェア サービス モジュール (HSM) または Azure Key Vault (AKV) を使用して、独自の暗号化キーを生成できます。 キーの生成方法に関係なく、AKV を使用して、Office 365によって使用される暗号化キーを制御および管理します。 キーが AKV に格納されたら、メールボックスデータまたはファイルを暗号化するキーチェーンのルートとして使用できます。

カスタマー キーのもう 1 つの利点は、Microsoft がデータを処理する機能を制御できることです。 Microsoft でサービスを終了する場合や、クラウドに保存されているデータの一部を削除する場合など、Office 365からデータを削除する場合は、カスタマー キーを技術コントロールとして使用できます。 データを削除すると、Microsoft を含む誰もデータにアクセスまたは処理できなくなります。 顧客キーは、Microsoft の担当者によるデータへのアクセスを制御するために使用するカスタマー ロックボックスに加えて補完的です。

Microsoft 365 for Exchange Online、Microsoft Teams、SharePoint Online (チーム サイト、OneDrive for Businessを含む) のカスタマー キーを設定する方法については、次の記事を参照してください。

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [カスタマー キーを設定する](customer-key-set-up.md)

- [カスタマー キーを管理する](customer-key-manage.md)

- [顧客キーまたは可用性キーをロールまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーについて理解する](customer-key-availability-key-understand.md)
