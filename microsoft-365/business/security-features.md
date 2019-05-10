---
title: Microsoft 365 Business セキュリティ機能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Microsoft 365 Business に付属しているセキュリティ機能について説明します。
ms.openlocfilehash: adf1cf183022f3d2c19364b9f60868e285f78637
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660582"
---
# <a name="microsoft-365-business-security-features"></a>Microsoft 365 Business セキュリティ機能

Microsoft 365 Business では、Pc、携帯電話、タブレットでデータを保護するための簡単なセキュリティ機能が提供されています。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business 管理センターのセキュリティ機能

![をhttps://aka.ms/aboutM365preview指すバナー。](media/m365admincenterchanging.png)

管理センターでは、Microsoft 365 Business セキュリティ機能の多くを管理することができます。これにより、これらの機能を簡単にオンまたはオフにすることができます。 管理センターでは、次の操作を実行できます。
  
![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
- [Android または iOS デバイスのアプリケーション管理設定を設定](app-protection-settings-for-android-and-ios.md)します。 
    
    これらの設定には、設定期間後に非アクティブなデバイスからファイルを削除する、作業ファイルを暗号化する、ユーザーに PIN を設定することなどが含まれます。
    
- [Windows 10 デバイスのアプリケーション保護設定を設定](protection-settings-for-windows-10-devices.md)します。 
    
    これらの設定は、会社所有のデバイスまたは個人所有のデバイスの両方で会社のデータに適用できます。
    
- [Windows 10 デバイスのデバイス保護設定を設定](protection-settings-for-windows-10-pcs.md)します。 
    
    デバイスが紛失または盗難にあった場合にデータを保護するために[BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)暗号化を有効にし、 [Windows Exploit Guard](https://go.microsoft.com/fwlink/p/?linkid=871404)がランサムウェアに対する高度な保護を提供できるようにします。 
    
- [デバイスから会社のデータを削除する](remove-company-data.md)
    
    デバイスが紛失、盗難、または従業員が退職した場合、会社のデータをリモートでワイプできます。
    
- [Windows 10 デバイスを出荷時の設定にリセット](reset-devices-to-factory-settings.md)します。 
    
    デバイス保護設定が適用されているすべての Windows 10 デバイスをリセットできます。
    
## <a name="additional-security-features"></a>その他のセキュリティ機能 

Microsoft 365 Business の高度な機能を使用すると、サイバー脅威からビジネスを保護し、機密情報を保護することができます。
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat Protection (ATP) は、従業員または顧客の情報を侵害するように設計された高度なフィッシングおよびランサムウェア攻撃からビジネスを保護するのに役に立ちます。 以下の機能があります。
    
  - 高度な添付ファイルスキャンと AI による分析により、危険なメッセージを検出して破棄します。
    
  - 電子メールの web リンクを自動チェックして、それらがフィッシング詐欺スキームの一部であるかどうかを評価します。 これにより、安全でない web サイトへのアクセスが安全に保たれます。
    
- **[データ損失防止ポリシーの概要](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    DLP を設定して、クレジットカード番号、社会保障番号などの機密情報を自動的に検出し、会社外との偶発的な共有を防ぐことができます。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online のアーカイブライセンスでは、継続的なデータバックアップを使用してメッセージを簡単にアーカイブできます。 削除済みアイテムを含むすべてのユーザーの電子メールを、後で検出または復元するときに必要に応じて保存します。 また、さまざまなアイテム保持ポリシーを使用して、訴訟ホールド、電子情報開示、またはコンプライアンス要件を満たすために電子メールデータを保持することができます。
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    情報保護は、「転送不可」や「コピーしない」などのコントロールを使用して、電子メールやドキュメント内の機密情報へのアクセスを制御するのに役に立ちます。 機密情報を "機密" として分類し、ビジネスの外部および内部で分類情報を共有する方法を指定することもできます。 エンタープライズレベルの暗号化は、情報の機密を保持するために電子メールやドキュメントに簡単に適用できます。 Microsoft 365 Business には、 [Azure Information Protection プラン 1](https://go.microsoft.com/fwlink/p/?linkid=871407)のすべての機能が含まれています。 Office アプリ用の Azure Information Protection クライアントアドインをインストールすることもできます。 詳細については、「 [Azure Information Protection クライアントの admininstrator ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)」を参照してください。
    
- **[Azure portal の Intune のすべての機能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure portal の Intune 管理センターにアクセスすることにより、Microsoft では提供されていない、Windows 用アドバンストデバイス管理と共に、MacOS デバイス、iPhone、Android デバイスの管理など、追加のセキュリティ機能を設定できます。365 Business 管理センター
    
次のセクションでは、これらの機能をセキュリティ&amp;コンプライアンスセンターおよび Intune 管理センターで管理する方法について説明します。 時間の経過とともに、簡略化された統制は Microsoft 365 Business 管理センターに追加されます。
  
    
## <a name="faq"></a>FAQ

 ### <a name="are-these-security-features-available-in-all-markets"></a>これらのセキュリティ機能はすべての市場で利用できますか?
  
はい。これらの機能は、Microsoft 365 Business が販売されているすべての市場で利用できます。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>セキュリティ&amp;コンプライアンスセンターを見つけるには、どうすればよいですか。
  
1. 管理者の資格情報を使用して、 [Microsoft 365 Business にサインイン](https://portal.microsoft.com/)します。 
    
2. 左側のナビゲーションで、[**管理センター** ] を見つけて展開します。 
    
    ![Microsoft 365 管理センターの左側のナビゲーションで、[管理センター] を選択します。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. [**セキュリティ&amp;コンプライアンス**] を選択し&amp;て、セキュリティ/コンプライアンスセンターに移動します。