---
title: Microsoft 365 Business security and コンプライアンス機能
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Microsoft 365 Business に付属しているセキュリティ機能について説明します。
ms.openlocfilehash: 8e45d5fdb6a78f3966c46542189aa30ddd80998e
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288457"
---
# <a name="microsoft-365-business-security-and-compliance-features"></a>Microsoft 365 Business security and コンプライアンス機能

Microsoft 365 Business では、Pc、携帯電話、タブレットでデータを保護するための簡単なセキュリティ機能が提供されています。
    
## <a name="microsoft-365-business-admin-center-security-features"></a>Microsoft 365 Business 管理センターのセキュリティ機能

[![[ラベル] 管理センターが変更されたことを知らせるために、aka.ms/aboutM365preview で詳細を確認できます。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

管理センターでは、Microsoft 365 Business セキュリティ機能の多くを管理することができます。これにより、これらの機能を簡単にオンまたはオフにすることができます。 管理センターでは、次の操作を実行できます。
  
  
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
    
  - 電子メール内のリンクの自動チェックを行い、それらがフィッシングスキームの一部であるかどうかを評価します。 これにより、安全でない web サイトへのアクセスが安全に保たれます。

- **[Azure portal の Intune のすべての機能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure portal の Intune 管理センターにアクセスすることにより、Microsoft では提供されていない、Windows 用アドバンストデバイス管理と共に、MacOS デバイス、iPhone、Android デバイスの管理など、追加のセキュリティ機能を設定できます。365 Business 管理センター
- **Azure AD P1 プランと同じ[条件付きアクセス](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)**

    条件付きアクセスでは、サインインリスクから組織を保護したり、予期しないネットワークまたはロケールからのアクセス試行、アクセス試行が危険なデバイスの種類などになったりすることを防止できます。 条件付きアクセスポリシーは、最初の認証が完了した後に適用され、最初の認証イベントからの信号を使用して、試行されたアクセスを承認、拒否、またはその他の証明 (2 番目の形式など) があるかどうかを判断します。必須。

    含まれている条件付きアクセス機能は次のとおりです。

    - ユーザー名、グループ、役割に基づくアクセス
    - [アプリに基づく](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access)アクセス 
    - [場所に基づいたアクセス](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)。 信頼された IP 範囲または特定の国からのアクセスのみを許可する 
    - アクセスに MFA を必要とする
    - [従来の認証](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)を使用するアプリへのアクセスをブロックする
    - アプリ tp が[Intune アプリ保護](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)を必要とする
    - サードパーティのプロバイダーを使用する MFA などのカスタム認証。たとえば、DUO。
   
    その他の機能:
    - ハイブリッド Azure AD の[セルフサービスによるパスワードのリセット](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)
    
## <a name="compliance-features"></a>コンプライアンス機能

Microsoft 365 Business サブスクリプションには、コンプライアンスおよび規制基準を維持するのに役立つ機能が含まれています。

- **[データ損失防止ポリシーの概要](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)**(DLP)。 
    
    DLP を設定して、クレジットカード番号、社会保障番号などの機密情報を自動的に検出し、会社外との偶発的な共有を防ぐことができます。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online のアーカイブライセンスでは、継続的なデータバックアップを使用してメッセージを簡単にアーカイブできます。 削除済みアイテムを含むすべてのユーザーの電子メールを、後で検出または復元するときに必要に応じて保存します。 また、さまざまなアイテム保持ポリシーを使用して、訴訟ホールド、電子情報開示、またはコンプライアンス要件を満たすために電子メールデータを保持することができます。
    
- **[Azure Information Protection](https://go.microsoft.com/fwlink/p/?linkid=871406)**
    
    情報保護は、「転送不可」や「コピーしない」などのコントロールを使用して、電子メールやドキュメント内の機密情報へのアクセスを制御するのに役に立ちます。 機密情報を "機密" として分類し、ビジネスの外部および内部で分類情報を共有する方法を指定することもできます。 エンタープライズレベルの暗号化は、情報の機密を保持するために電子メールやドキュメントに簡単に適用できます。 Microsoft 365 Business には、 [Azure Information Protection プラン 1](https://go.microsoft.com/fwlink/p/?linkid=871407)のすべての機能が含まれています。 Office アプリ用の Azure Information Protection クライアントアドインをインストールすることもできます。 詳細については、「 [Azure Information Protection クライアント管理者ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/client-admin-guide)」を参照してください。

これらの機能は、セキュリティ&amp;コンプライアンスセンターおよび Intune 管理センターで管理できます。 時間の経過とともに、簡略化された統制は Microsoft 365 Business 管理センターに追加されます。
  
    
## <a name="faq"></a>FAQ

 ### <a name="are-these-security-features-available-in-all-markets"></a>これらのセキュリティ機能はすべての市場で利用できますか?
  
はい。これらの機能は、Microsoft 365 Business が販売されているすべての市場で利用できます。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>セキュリティ&amp;コンプライアンスセンターを見つけるには、どうすればよいですか。
  
1. 管理者の資格情報を使用して、 [Microsoft 365 Business にサインイン](https://portal.microsoft.com/)します。 
    
2. 左側のナビゲーションで、[**管理センター** ] を見つけて展開します。 
    
    ![Microsoft 365 管理センターの左側のナビゲーションで、[管理センター] を選択します。](media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. [**セキュリティ&amp;コンプライアンス**] を選択し&amp;て、セキュリティ/コンプライアンスセンターに移動します。