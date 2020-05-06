---
title: サード パーティのデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 メールボックスにサードパーティのデータをインポートする方法について説明します。
ms.openlocfilehash: 0db7019b607388b7c62fe19210b85b8410083f32
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035485"
---
# <a name="archive-third-party-data"></a>サード パーティのデータをアーカイブする

Microsoft 365 では、管理者がソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。 Microsoft 365 にインポートできるサードパーティのデータソースの例には、次のサービスが含まれています。 
  
- **ソーシャル:** Facebook、LinkedIn、Twitter、Yammer

- **インスタントメッセージング:** Yahoo メッセンジャーと GoogleTalk

- **ドキュメントの共同作業:** Box および DropBox

- **縦型の業種:** 顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など)

- **SMS/テキストメッセージング:** BlackBerry

サードパーティのデータがインポートされた後は、訴訟ホールド、電子情報開示、インプレースアーカイブ、監査、通信コンプライアンス、およびアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能をこのデータに適用することができます。 たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。 Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。 また、Microsoft データの場合と同じように、アーカイブポリシーとアイテム保持ポリシーをサードパーティデータに適用することができます。 簡単に言えば、Microsoft 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

Microsoft 365 でサードパーティのデータをインポートしてアーカイブする方法は2つあります。

- **セキュリティ & コンプライアンスセンターで、サードパーティのデータコネクタを使用します。** Microsoft 365 コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。 コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Microsoft 365 のメールボックスにアイテムがインポートされます。 現時点では、Facebook ビジネスページ、企業 Twitter アカウント、LinkedIn、Instant Bloomberg、組織の人事 (HR) データのデータをインポートおよびアーカイブするためのコネクタを実装できます。 これらのコネクタの1つを設定するための詳しい手順については、以下を参照してください。

   - **Facebook:** [コネクタを使用して Facebook データをアーカイブする](archive-facebook-data-with-sample-connector.md)

   - **Twitter:** [コネクタを使用して twitter データをアーカイブする](archive-twitter-data-with-sample-connector.md)

   - **Linkedin:** [linkedin データをアーカイブするためのコネクタを設定する](archive-linkedin-data.md)

   - **インスタント Bloomberg:** [インスタント Bloomberg データをアーカイブするためのコネクタの設定](archive-instant-bloomberg-data.md)

   - **人事データ:** [hr データをインポートするためのコネクタを設定する](import-hr-data.md)

- **Microsoft パートナーと連携する:** 組織は、サードパーティのデータソースからアイテムを定期的に抽出するように構成されるカスタムコネクタを提供する Microsoft パートナーと連携して、サードパーティの API によって Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートします。 また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Microsoft 365 のメールボックスにインポートします。 この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「 [Microsoft 365 でサードパーティのデータをアーカイブするためにパートナーと連携する](work-with-partner-to-archive-third-party-data.md)」を参照してください。
