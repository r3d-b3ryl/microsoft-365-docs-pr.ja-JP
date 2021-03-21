---
title: Microsoft Managed Desktop のセキュリティ テクノロジ
description: デバイス セキュリティ、ID およびアクセス管理、ネットワーク セキュリティ、および情報セキュリティに使用されるテクノロジ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b1111f0867ff9a49ba670cdd8b48d10d158fd3ed
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917772"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop のセキュリティ テクノロジ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop は、いくつかの Microsoft テクノロジを使用して、管理対象デバイスとデータのセキュリティ保護に役立ちます。 さらに、Microsoft Managed Desktop Security Operations Center では、これらのテクノロジと組み合 [わせて](security-operations.md) さまざまなプロセスを使用します。

具体的には次のとおりです。 

- [デバイスのセキュリティ](#device-security) – Microsoft Managed Desktop デバイスのセキュリティと保護
- [ID とアクセス管理](#identity-and-access-management) – Azure Active Directory ID サービスを通じてデバイスの安全な使用を管理する
- [ネットワーク セキュリティ](#network-security) – VPN 情報と Microsoft Managed Desktop 推奨ソリューションと設定
- [情報セキュリティ](#information-security) – 機密情報をさらに保護するためのオプションの利用可能なサービス 

Microsoft Managed Desktop で使用されるデータストレージ、使用状況、およびセキュリティプラクティスの詳細については、以下のホワイトペーパーを参照してください [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>デバイスのセキュリティ

Microsoft Managed Desktop では、すべての管理対象デバイスがセキュリティで保護され、次のサービスを使用して、可能な限り早期に脅威を検出します。

サービス | 説明
--- | ---
ウイルス対策 | Microsoft Defender AV がインストールされ、構成されている<br>Microsoft Defender AV の定義は最新の情報です
ボリューム全体の暗号化 |    Windows BitLocker は、Microsoft Managed Desktop デバイスのボリューム暗号化ソリューションです。<br><br>組織がサービスにオンボードすると、デバイスがスリープ モードまたはオフのときにローカル データへの不正アクセスを防止するために、組み込みの信頼プラットフォーム モジュール (TPM) を備えた Windows BitLocker を使用してデバイスが暗号化されます。 
監視 |    Microsoft Defender for Endpoint は、すべての Microsoft Managed Desktop デバイスでセキュリティ脅威の監視に使用されます。 Defender for Endpoint を使用すると、企業のお客様は、企業ネットワーク内の高度な脅威を検出、調査、および対応できます。 詳細については [、「Microsoft Defender for Endpoint」を参照してください。](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
オペレーティング システムの更新 |  Microsoft Managed Desktop デバイスは、常に最新のセキュリティ更新プログラムで保護されます。
Secure Device Configuration |   Microsoft Managed Desktop は、Microsoft セキュリティ ベースラインを実装します。 詳細については、「Windows セキュリティ基準 [」を参照してください。](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>ID およびアクセス管理

ID とアクセス管理は、企業の資産とビジネスクリティカルなデータを保護します。 Microsoft Managed Desktop は、Azure Active Directory (Azure Active Directory) 管理 ID で安全に使用AD構成します。 Azure テナントで正確な情報を維持する責任は、お客様ADです。 

サービス | 説明
--- | ---
生体認証 |  Windows Hello を使用すると、ユーザーは顔または PIN を使用してサインインし、パスワードを忘れや盗みにくくすることができます。 お客様は、ハイブリッド構成でこのサービスを使用するために、オンプレミスの Active Directory に必要な前提条件を実装する責任があります。 詳細については [、「Windows Hello」を参照してください。](/windows-hardware/design/device-experiences/windows-hello) 
標準ユーザーのアクセス許可 |  システムを保護し、セキュリティを高くするために、ユーザーには Standard User Permissions が割り当てられます。 このアクセス許可は、Windows Autopilot のアウトオブボックス エクスペリエンスの一部として割り当てられます。



## <a name="network-security"></a>ネットワーク セキュリティ

お客様はネットワーク セキュリティを担当します。 

サービス | 説明
--- | ---
VPN | 制限された企業リソースをイントラネットの外部に公開できるよう、お客様は VPN インフラストラクチャを所有しています。<br><br>最小要件: Microsoft Managed Desktop には、Windows 10 互換でサポートされている VPN ソリューションが必要です。 組織で VPN ソリューションが必要な場合は、Windows 10 をサポートし、Intune を通じてパッケージ化して展開できる必要があります。 詳細については、ソフトウェア発行元にお問い合わせください。<br><br>推奨事項:<br>- Microsoft では、VPN プロファイルをプッシュするために Intune を介して簡単に展開できる最新の VPN ソリューションをお勧めします。 このアプローチは、企業ネットワークにアクセスするための常時オン、シームレス、信頼性、および安全な方法を提供します。 詳細については、「Intune の [VPN 設定」を参照してください](/intune/vpn-settings-configure)。<br>- 厚い VPN クライアント、または古い VPN クライアントは、ユーザー環境に影響を与える可能性がある Microsoft Managed Desktop を使用している間、Microsoft によって推奨されません。<br>- 送信 Web トラフィックは、パフォーマンスの問題を回避するために VPN を経由せずにインターネットに直接送信する必要があります。<br>- 理想的には、VPN ではなく Azure Active Directory アプリ プロキシの使用をお勧めします。


## <a name="information-security"></a>情報セキュリティ

企業の価値の高い資産を保護するために、これらのオプション サービスを構成できます。 

サービス | 説明
--- | ---
データ復旧  | デバイス上のキー フォルダーに格納されている情報は、OneDrive for Business にバックアップされます。 Microsoft Managed Desktop は、OneDrive for Business と同期されていないデータに対して責任を負いません。 
Windows 情報保護 |    高レベルの情報セキュリティが必要な企業では [、Windows Information Protection](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) と Azure Information [Protection をお勧めします](https://www.microsoft.com/cloud-platform/azure-information-protection)。