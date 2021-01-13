---
title: Microsoft 365 Business Premium のセキュリティおよびコンプライアンス機能
f1.keywords:
- NOCSH
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
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: PC、電話、タブレット上のデータを保護するために Microsoft 365 Business Premium に備わるセキュリティ機能について説明します。
ms.openlocfilehash: b7fdd3d7fa25c23ee49ae82aa037588d8fba61a1
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840391"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium のセキュリティおよびコンプライアンス機能

Microsoft 365 Business Premium は、PC、電話、タブレット上のデータを保護するために、簡素化されたセキュリティ機能を提供します。
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 管理センターのセキュリティ機能

管理センターでは、Microsoft 365 Business Premium のセキュリティ機能の多くを管理できます。これにより、これらの機能を簡単に有効またはオフにできます。 管理センターでは、次の操作を実行できます。
  
- [Android または iOS デバイスのアプリケーション管理設定を設定します](app-protection-settings-for-android-and-ios.md) 。 
    
    これらの設定には、設定期間が終了した後の非アクティブなデバイスからのファイルの削除、作業ファイルの暗号化、ユーザーによる PIN の設定の要求が含まれます。
    
- [Windows 10 デバイスのアプリケーション保護設定を設定します](protection-settings-for-windows-10-devices.md) 。 
    
    これらの設定は、会社が所有するデバイスまたは個人所有のデバイスの両方の会社データに適用できます。
    
- [Windows 10 デバイスのデバイス保護設定を設定します](protection-settings-for-windows-10-pcs.md) 。 
    
    [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405)暗号化を有効にして、デバイスが紛失または盗難に備え、データを保護し[、Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection)を有効にしてランサムウェアに対する高度な保護を提供できます。 
    
- [デバイスから会社のデータを削除する](remove-company-data.md)
    
    デバイスが紛失したり盗まれたり、従業員が会社を離れた場合は、会社のデータをリモートで消去できます。
    
- [Windows 10 デバイスを工場出荷時の設定にリセットします](reset-devices-to-factory-settings.md) 。 
    
    デバイス保護設定が適用されている Windows 10 デバイスをリセットできます。
    
## <a name="additional-security-features"></a>その他のセキュリティ機能 

Microsoft 365 Business Premium の高度な機能を使用すると、サイバー アタックからビジネスを保護し、機密情報を保護できます。
  
- **[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Microsoft Defender for Office 365 は、従業員や顧客情報を侵害するように設計された高度なフィッシング攻撃やランサムウェア攻撃からビジネスを保護するのに役立ちます。 以下の機能があります。
    
  - 危険なメッセージを検出して破棄する高度な添付ファイル スキャンと AI による分析。
    
  - メール内のリンクがフィッシング詐欺の一部である場合に評価するための自動チェック。 これにより、安全でない Web サイトへのアクセスを安全に行います。

- **[Azure portal での Intune の完全な機能](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure Portal で Intune 管理センターにアクセスすると、Microsoft 365 管理センターでは利用できない、Windows 用の高度なデバイス管理と共に、MacOS デバイス、iPhone、Android デバイスの管理などの追加のセキュリティ機能を設定できます。
- **Azure [AD](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Premium P1 プランと同じ条件付きアクセス**


    条件付きアクセスは、サインインのリスク、予期しないネットワークまたはロケールからのアクセス試行、危険なデバイスの種類からのアクセス試行などから組織を保護するのに役立ちます。 条件付きアクセス ポリシーは、最初の認証が完了した後に適用され、最初の認証イベントからのシグナルを使用して、試行されたアクセスを承認、拒否、またはより多くの証明 (2 番目の形式の識別など) が必要かどうかを判断します。

    含まれる条件付きアクセス機能は次のとおりです。

    - ユーザー名、グループ、ロールに基づくアクセス
    - アプリ [に基づくアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [場所に基づくアクセス](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration) 信頼できる IP 範囲または特定の国からのアクセスのみを許可する 
    - アクセスに MFA を要求する
    - レガシ認証を使用するアプリへの [アクセスをブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Intune アプリ保護を使用 [するアプリを要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - サード パーティプロバイダーを使用した MFA などのカスタム認証 (例: MFA)。
   
    その他の機能:
    - ハイブリッド Azure[アプリケーションのセルフサービス](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization)によるパスワードのリセットAD
    
## <a name="compliance-features"></a>コンプライアンス機能

Microsoft 365 Business Premium サブスクリプションには、コンプライアンスと規制基準の維持に役立つ機能が含まれています。

- **[データ損失防止ポリシー (DLP) の](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** 概要。 
    
    DLP を設定して、クレジット カード番号、社会保障番号などの機密情報を自動的に検出し、会社外での不注意による共有を防止できます。
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archivingライセンスを使用すると、継続的なデータ バックアップを使用してメッセージを簡単にアーカイブできます。 後で検出または復元に必要な場合に備え、削除済みアイテムを含むすべてのユーザーの電子メールを格納します。 さらに、さまざまなアイテム保持ポリシーを使用して、訴訟ホールド、電子情報開示、またはコンプライアンス要件を満たす電子メール データを保持できます。
    
- **[秘密度ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium には [、Azure Information Protection プラン 1 のすべての機能が含まれています](https://go.microsoft.com/fwlink/p/?linkid=871407)。 このプランでは、「転送しない」や「コピーしない」などのコントロールを使用して、電子メールやドキュメント内の機密情報へのアクセスを制御できる機密ラベルを作成できます。 機密情報を "社外秘" として分類し、機密情報をビジネスの外部と内部で共有する方法を指定できます。 エンタープライズ レベルの暗号化は、電子メールやドキュメントに簡単に適用して、情報を非公開にできます。 また、Azure Information Protection クライアント アドインを新しいアプリOfficeすることもできます。 詳細については [、「Azure Information Protection 統合ラベル付けクライアント」を参照してください](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)。 [Sensitivity] ラベルの場合は、次 **のAzInfoProtection_UL.exe。**

これらの機能は、セキュリティ コンプライアンス センターと &amp; Intune 管理センターで管理できます。 時間の長い間、簡素化されたコントロールが Microsoft 365 管理センターに追加されます。
  
    
## <a name="faq"></a>よくあるご質問 (FAQ)

 ### <a name="are-these-security-features-available-in-all-markets"></a>これらのセキュリティ機能は、すべての市場で利用できますか?
  
はい。これらの機能は、Microsoft 365 Business Premium が販売されているすべての市場で利用できます。
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>セキュリティ コンプライアンス センターを &amp; 見つける方法
  
1. [管理者の資格情報を使用して Microsoft 365 Business Premium](https://portal.microsoft.com/) にサインインします。 
    
2. 左側のナビゲーションで、管理センター **を見つけて** 展開します。 
    
    ![Microsoft 365 管理センターの左側のナビゲーションで、[管理センター] を選択します。](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. [ **セキュリティ コンプライアンス &amp; ] を** 選択して、セキュリティ コンプライアンス センター &amp; に移動します。
