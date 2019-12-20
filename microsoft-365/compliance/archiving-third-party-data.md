---
title: サードパーティのデータをアーカイブする
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
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理者は、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートできます。 これにより、Office 365 で Facebook、Twitter、およびその他のサードパーティのデータソースからデータをアーカイブすることができます。 その後、サードパーティデータの Office 365 コンプライアンス機能 (法的情報保留、電子情報開示、インプレースアーカイブ、アイテム保持ポリシーなど) を使用して適用することができます。
ms.openlocfilehash: 10ec436887816080716ecd8870e2b2da8021e9af
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807466"
---
# <a name="archive-third-party-data"></a>サードパーティのデータをアーカイブする

Office 365 を使用すると、管理者はソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Office 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。 Office 365 にインポートできるサードパーティのデータソースの例としては、次のサービスがあります。 
  
- **ソーシャル:** Facebook、LinkedIn、Twitter、Yammer 
    
- **インスタントメッセージング:** Yahoo! メッセンジャー、GoogleTalk、および Cisco Jabber 
    
- **ドキュメントの共同作業:** Box および DropBox 
    
- **縦型の業種:** 顧客関係管理 (Salesforce チャターなど)、金融サービス (Bloomberg、Thomson Reuters など) 
    
- **SMS/テキストメッセージング:** BlackBerry 
    
サードパーティのデータがインポートされたら、訴訟ホールド、電子情報&mdash;開示、インプレースアーカイブ、監査、[通信コンプライアンス](communication-compliance.md)、office 365 アイテム保持ポリシー&mdash;などの office 365 コンプライアンス機能をこのデータに適用することができます。 たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。 Microsoft eDiscovery ツールを使用して、サードパーティのデータを検索できます。 また、Microsoft データの場合と同じように、アーカイブポリシーとアイテム保持ポリシーをサードパーティデータに適用することができます。 簡単に言えば、Office 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

Office 365 でサードパーティのデータをインポートしてアーカイブするには、次の2つの方法があります。

- **セキュリティ & コンプライアンスセンターで、サードパーティのデータコネクタを使用します。** Office 365 のセキュリティ & コンプライアンスセンターで利用可能なカスタムデータコネクタを使用します。 コネクタをセットアップして構成すると、サードパーティのデータソースに接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、Office 365 のメールボックスにアイテムがインポートされます。 現時点では、Facebook のビジネスページ、企業 Twitter アカウント、インスタント Bloomberg、LinkedIn からデータをインポートしてアーカイブするためのコネクタを実装できます。 コネクタを設定するための詳しい手順については、以下を参照してください。
   
   - **Facebook:** [サンプルコネクタを使用して Office 365 で Facebook データをアーカイブする](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter:** [サンプルコネクタを使用して Office 365 で Twitter データをアーカイブする](archive-twitter-data-with-sample-connector.md)
    
   - **Linkedin:** [Office 365 で linkedin データをアーカイブするためのコネクタを設定する](archive-linkedin-data.md)

   - **インスタント Bloomberg:** [Office 365 でインスタント Bloomberg データをアーカイブするためのコネクタの設定](archive-instant-bloomberg-data.md)

- **Microsoft パートナーと連携する:** 組織は、サードパーティのデータソースからアイテムを定期的に抽出するように構成されるカスタムコネクタを提供する Microsoft パートナーと連携して、サードパーティの API によって Microsoft クラウドに接続し、それらのアイテムを Office 365 にインポートします。 また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Office 365 のメールボックスにインポートします。 この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「Office を使用して[サードパーティデータをアーカイブする 365](work-with-partner-to-archive-third-party-data.md)」を参照してください。
