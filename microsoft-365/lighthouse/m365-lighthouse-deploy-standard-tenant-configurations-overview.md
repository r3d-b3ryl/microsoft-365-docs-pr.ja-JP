---
title: 基準計画を使用した標準テナント構成の展開の概要
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseを使用して標準テナント構成を展開する方法について説明します。
ms.openlocfilehash: f59ca686892e0b20ce5e9ffb6d62859ce8079896
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323151"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>基準計画を使用した標準テナント構成の展開の概要 

Microsoft 365 Lighthouseベースラインを使用すると、複数の顧客テナント間でセキュリティ設定Microsoft 365管理できる、反復可能で拡張性の高い方法が提供されます。 ベースラインは、ユーザー、デバイス、およびデータをセキュリティで保護する構成を使用して、コア セキュリティ ポリシーとテナントコンプライアンス標準を監視するのにも役立ちます。

Managed Service Providers (MSP) が顧客によるセキュリティの導入を可能にするように設計されたライトハウスは、標準のベースライン パラメーターセットと、Microsoft 365 サービス用の事前定義された構成を提供します。 これらのセキュリティ構成は、テナントのセキュリティとコンプライアンスMicrosoft 365を測定するのに役立ちます。

既定の基準計画とその展開手順は、ライトハウス内から表示できます。 基準計画をテナントに適用するには、左側のナビゲーション ウィンドウで **[テナント** ] を選択し、テナントを選択します。 次に、[展開計画] **タブに移動** し、ベースラインを実装します。

## <a name="default-baseline-security-templates"></a>既定の基準計画のセキュリティ テンプレート

セキュリティ ワークロードのライトハウスの既定のベースライン構成は、すべての管理テナントが安全で準拠するように設計されています。

次の表のベースライン構成には、ライトハウスの既定の基準計画が標準で示されています。<br><br>

| ベースライン構成 | 説明 |
|--|--|
| 管理者に MFA を要求する | すべての管理者に対して多要素認証を必要とする条件付きアクセス ポリシー。 すべてのクラウド アプリケーションに必要です。 この基準の詳細については、「条件付きアクセス [: すべての管理者に MFA を要求する」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)。|
| エンド ユーザーに MFA を要求する | すべてのユーザーに対して多要素認証を必要とする条件付きアクセス ポリシー。  すべてのクラウド アプリケーションに必要です。 この基準の詳細については、「条件付きアクセス [: すべてのユーザーに MFA を要求する」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。 |
| 従来の認証をブロックする | 従来のクライアント認証をブロックする条件付きアクセス ポリシー。 この基準の詳細については、「条件付きアクセスを使用して従来の[認証Azure ADをブロックする」を参照してください](/azure/active-directory/conditional-access/block-legacy-authentication)。|
| デバイスの登録を設定する | テナント デバイスがデバイスに登録できるデバイスMicrosoft エンドポイント マネージャー。 これは、ユーザーとユーザーの間で自動登録Azure Active Directory設定Microsoft エンドポイント マネージャー。 この基準の詳細については、「デバイスの登録を[設定する」をWindowsしてください](/mem/intune/enrollment/windows-enroll)。 |
| デバイスMicrosoft Defender ウイルス対策以降のWindows 10構成する | 事前に構成されたデバイスWindowsデバイスのデバイス構成プロファイルMicrosoft Defender ウイルス対策します。 この基準の詳細については、「 [Configure Microsoft Defender for Endpoint in Intune」を参照してください](/mem/intune/protect/advanced-threat-protection-configure)。|
| Microsoft Defender Firewall for Windows 10以降 | 望ましくないネットワーク トラフィックと承認されていないネットワーク トラフィックを防止してデバイスをセキュリティで保護するためのファイアウォール ポリシー。 この基準の詳細については、「ファイアウォールを構成するためのベスト プラクティス」[をWindows Defenderしてください](/windows/security/threat-protection/windows-firewall/best-practices-configuring)。  |
| デバイス コンプライアンス ポリシーを構成して、Windows 10以降に設定する | 基本的Windows要件を満たす、事前に構成された設定を持つデバイス ポリシーです。 この基準の詳細については、「条件付きアクセス: 参加しているデバイスに準拠しているデバイスまたは[ハイブリッド Azure ADする」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。 |


## <a name="related-content"></a>関連コンテンツ

[ベースラインMicrosoft 365 Lighthouse展開](m365-lighthouse-deploy-baselines.md)する (記事)\
[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
