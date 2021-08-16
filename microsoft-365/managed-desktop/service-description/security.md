---
title: セキュリティ テクノロジ (Microsoft マネージド デスクトップ
description: デバイス セキュリティ、ID およびアクセス管理、ネットワーク セキュリティ、および情報セキュリティに使用されるテクノロジ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4b0399adae82123bf4e0d6ca5aa462d1b48ac80e9143b6744e936a6b94554c68
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854413"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>セキュリティ テクノロジ (Microsoft マネージド デスクトップ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft マネージド デスクトップは、いくつかの Microsoft テクノロジを使用して、管理対象デバイスとデータのセキュリティ保護に役立ちます。 さらに、セキュリティ 運用センター Microsoft マネージド デスクトップこれらのテクノロジと組み[合わせてさまざまな](security-operations.md)プロセスを使用します。

具体的には次のとおりです。

- [デバイス のセキュリティ](#device-security)– デバイスのセキュリティとMicrosoft マネージド デスクトップ保護
- [ID とアクセス管理](#identity-and-access-management)– ID サービスを通じてデバイスの安全な使用Azure Active Directory管理する
- [ネットワーク セキュリティ](#network-security)– VPN 情報とMicrosoft マネージド デスクトップ推奨されるソリューションと設定
- [情報セキュリティ](#information-security) – 機密情報をさらに保護するためのオプションの利用可能なサービス

データストレージ、使用状況、およびセキュリティプラクティスについては、Microsoft マネージド デスクトップホワイトペーパーを参照してください [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>デバイスのセキュリティ

Microsoft マネージド デスクトップすべての管理対象デバイスがセキュリティで保護され、次のサービスを使用して可能な限り早期に脅威を検出します。

サービス | 説明
--- | ---
ウイルス対策 | Microsoft Defender AV がインストールされ、構成されている<br>Microsoft Defender AV の定義は最新の情報です
ボリューム全体の暗号化 | WindowsBitLocker は、デバイスのボリューム暗号化Microsoft マネージド デスクトップです。<br><br>組織がサービスにオンボードされた後、デバイスは、Windows BitLocker と組み込みの信頼プラットフォーム モジュール (TPM) を使用して暗号化され、デバイスがスリープ モードまたはオフのときにローカル データへの不正アクセスを防止します。
監視 | Microsoft Defender for Endpoint は、すべてのデバイスでセキュリティ脅威の監視Microsoft マネージド デスクトップされます。 Defender for Endpoint を使用すると、企業のお客様は、企業ネットワーク内の高度な脅威を検出、調査、および対応できます。 詳細については [、「Microsoft Defender for Endpoint」を参照してください。](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
オペレーティング システムの更新 | Microsoft マネージド デスクトップデバイスは、常に最新のセキュリティ更新プログラムでセキュリティ保護されます。
Secure Device Configuration | Microsoft マネージド デスクトップ Microsoft セキュリティ ベースラインを実装します。 詳細については、「セキュリティベースライン[Windows参照してください。](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>ID およびアクセス管理

ID とアクセス管理は、企業の資産とビジネスクリティカルなデータを保護します。 Microsoft マネージド デスクトップ Azure Active Directory (Azure AD) マネージ ID で安全に使用するようにデバイスを構成します。 Azure テナントで正確な情報を維持する責任は、お客様ADです。

サービス | 説明
--- | ---
生体認証 | Windows Helloは、ユーザーが自分の顔または PIN を使用してサインインし、パスワードを忘れにくくしたり盗んだりすることを可能にしています。 お客様は、ハイブリッド構成でこのサービスを使用するために、オンプレミスの Active Directory に必要な前提条件を実装する責任があります。 詳細については[、「Windows Hello」を参照してください。](/windows-hardware/design/device-experiences/windows-hello) 
標準ユーザーのアクセス許可 | システムを保護し、セキュリティを高くするために、ユーザーには Standard User Permissions が割り当てられます。 このアクセス許可は、Autopilot Windowsエクスペリエンスの一部として割り当てられます。



## <a name="network-security"></a>ネットワーク セキュリティ

お客様はネットワーク セキュリティを担当します。 

サービス | 説明
--- | ---
VPN | 制限された企業リソースをイントラネットの外部に公開できるよう、お客様は VPN インフラストラクチャを所有しています。<br><br>最小要件: 互換性Microsoft マネージド デスクトップサポートWindows 10 VPN ソリューションが必要です。 組織で VPN ソリューションが必要な場合は、Intune を介してパッケージ化Windows 10展開可能な VPN ソリューションをサポートする必要があります。 詳細については、ソフトウェア発行元にお問い合わせください。<br><br>推奨事項:<br>- Microsoft では、VPN プロファイルをプッシュするために Intune を介して簡単に展開できる最新の VPN ソリューションをお勧めします。 このアプローチは、企業ネットワークにアクセスするための常時オン、シームレス、信頼性、および安全な方法を提供します。 詳細については、「Intune の [VPN 設定」を参照してください](/intune/vpn-settings-configure)。<br>- 厚い VPN クライアント、または古い VPN クライアントは、ユーザー環境に影響を与える可能性Microsoft マネージド デスクトップを使用している間、Microsoft では推奨されません。<br>- 送信 Web トラフィックは、パフォーマンスの問題を回避するために VPN を経由せずにインターネットに直接送信する必要があります。<br>- 理想的には、VPN ではなくアプリ プロキシAzure Active Directory使用をお勧めします。


## <a name="information-security"></a>情報セキュリティ

企業の価値の高い資産を保護するために、これらのオプション サービスを構成できます。 

サービス | 説明
--- | ---
データ復旧  | デバイス上のキー フォルダーに格納されている情報は、OneDrive for Business。 Microsoft マネージド デスクトップデータと同期されていないデータについては、一OneDrive for Business。
Windows 情報保護 | 高レベルの情報セキュリティが必要な企業の場合は、情報保護Windows Azure [Information Protection を](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)[使用することをお勧めします。](https://www.microsoft.com/cloud-platform/azure-information-protection)
