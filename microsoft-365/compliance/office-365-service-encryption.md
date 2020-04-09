---
title: Office 365 でのサービスの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365 のサービス層でのデータ暗号化について説明します。'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193463"
---
# <a name="office-365-service-encryption"></a>Office 365 でのサービスの暗号化

BitLocker をボリュームレベルの暗号化に使用することに加えて、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams でも、サービス暗号化を使用して顧客データを暗号化します。 サービス暗号化では、2つの主要な管理オプションを使用できます。

- Microsoft は、すべての暗号化キーを管理します。 このオプションは現在、SharePoint Online、OneDrive for Business、Skype for business、および Teams のチャットで利用できます。 データは、Microsoft の管理キーを使用して既定で暗号化されます。

- 組織がルートキーを提供します。 これらのキーは、Azure Key Vault を使用して管理します。 このオプションは、顧客キーと呼ばれます。 顧客キーは現在、Exchange Online、SharePoint Online、OneDrive for business、Skype for Business、および Teams ファイルで使用できます。 顧客キーを使用する場合、これらのキーは Microsoft マネージキーを置き換えてデータを暗号化します。

選択したオプションに関係なく、サービス暗号化には複数の利点があります。

- 承認済みユーザーによって要求されたデータを取得して復号化するために、ユーザー認証を適用します。

- Windows オペレーティングシステム管理者と、オペレーティングシステムによって保存または処理される顧客データへのアクセスを分離します。

- 暗号化に関するコンプライアンス要件を持つお客様の要求を満たす Office 365 の能力を向上させます。

Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、および Teams の各ファイルに対して Office 365 の顧客キーを設定する方法については、次の記事を参照してください。

- [Office 365 での顧客キーによるサービスの暗号化](customer-key-overview.md)

- [Office 365 の顧客キーを設定する](customer-key-set-up.md)

- [Office 用の顧客キーの管理365](customer-key-manage.md)

- [顧客キーまたは可用性キーをロールまたは回転する](customer-key-availability-key-roll.md)

- [可用性キーについて理解する](customer-key-availability-key-understand.md)
