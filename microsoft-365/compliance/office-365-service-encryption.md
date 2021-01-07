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
description: '概要: Microsoft Office 365 のデータ復元について説明します。'
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777052"
---
# <a name="service-encryption"></a>サービスの暗号化

ボリューム レベルの暗号化に加えて、Exchange Online、Skype for Business、SharePoint Online、および OneDrive for Business は、顧客データの暗号化にサービス暗号化も使用します。 サービスの暗号化では、次の 2 つの主要な管理オプションを使用できます。

## <a name="microsoft-managed-keys"></a>Microsoft が管理するキー
Microsoft では、サービス暗号化のルート キーを含むすべての暗号化キーを管理しています。 このオプションは現在、Exchange Online、SharePoint Online、OneDrive for Business で既定で有効になっています。 Microsoft で管理されるキーは、カスタマー キーを使用してオンボードしない限り、既定のサービス暗号化を提供します。 後日、データ消去パスに従わずに顧客キーの使用を停止する場合、データは Microsoft が管理するキーを使用して暗号化されたままとなります。 データは、少なくともこの既定のレベルで常に暗号化されます。 

## <a name="customer-key"></a>顧客キー
サービスの暗号化で使用するルート キーを指定し、Azure Key Vault を使用してこれらのキーを管理します。 Microsoft は、他のすべてのキーを管理します。 このオプションは顧客キーと呼ばされ、現在 Exchange Online、SharePoint Online、OneDrive for Business で使用できます。 (以前は BYOK を使用した Advanced Encryption と呼ばばていました。 最初 [のお知らせについては、365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) Officeの透明性とコントロールの強化に関するページをご覧ください)。

サービスの暗号化には、次の複数の利点があります。

- BitLocker の上に保護の層を追加します。

- Windows オペレーティング システム管理者が、オペレーティング システムによって保存または処理されたアプリケーション データへのアクセスから分離します。

- マルチテナント サービスがテナント単位のキー管理を提供できる顧客キー オプションが含まれています。

- 暗号化に関する特定のコンプライアンス要件を持つお客様の要求に応える Microsoft 365 の機能を強化します。

顧客キーを使用すると、オンプレミスのハードウェア サービス モジュール (VAULT) または Azure Key Vault (A VAULT) のいずれかを使用して、独自の暗号化キーを生成できます。 キーの生成方法に関係なく、ARK を使用して、365 で使用される暗号化キーをOfficeします。 キーを ARK に保存したら、メールボックスのデータまたはファイルを暗号化するキーチェーンのルートとして使用できます。

顧客キーのもう 1 つの利点は、Microsoft がデータを処理する機能を制御する方法です。 Office 365 からデータを削除する場合 (Microsoft とのサービスを終了する場合や、クラウドに保存されているデータの一部を削除する場合など) は、その操作を行い、テクニカル コントロールとして顧客キーを使用できます。 データを削除すると、Microsoft を含む誰もデータにアクセスしたり処理したりしなけずに行う必要があります。 カスタマー キーは、Microsoft の担当者によるデータへのアクセスを制御するために使用するカスタマー ロックボックスに加えて補完的です。

Microsoft 365 for Exchange Online、Skype for Business、SharePoint Online (チーム サイト、OneDrive for Business を含む) のカスタマー キーをセットアップする方法については、次の記事を参照してください。

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [顧客キーの設定](customer-key-set-up.md)

- [顧客キーの管理](customer-key-manage.md)

- [顧客キーまたは可用性キーをロールまたはローテーションする](customer-key-availability-key-roll.md)

- [可用性キーを理解する](customer-key-availability-key-understand.md)

