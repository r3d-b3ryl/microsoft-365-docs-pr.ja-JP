---
title: Microsoft マネージド デスクトップのセキュリティ テクノロジ
description: デバイス のセキュリティ、ID とアクセスの管理、ネットワーク セキュリティ、および情報セキュリティに使用されるテクノロジ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840915"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのセキュリティ テクノロジ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft マネージド デスクトップでは、いくつかの Microsoft テクノロジを使用して、管理対象のデバイスとデータをセキュリティで保護します。 さらに、Microsoft マネージド デスクトップ セキュリティ 運用センターでは、これらのテクノロジと組み合 [わせて](security-operations.md) さまざまなプロセスを使用します。

具体的には次のとおりです。 

- [デバイスのセキュリティ](#device-security) – Microsoft マネージド デスクトップ デバイスでのセキュリティと保護
- [ID とアクセス管理](#identity-and-access-management) – Azure Active Directory ID サービスを介してデバイスの安全な使用を管理する
- [ネットワーク セキュリティ](#network-security) - VPN 情報と Microsoft マネージド デスクトップの推奨ソリューションと設定
- [情報セキュリティ](#information-security) – 機密情報をさらに保護するためのオプションの利用可能なサービス 

Microsoft マネージド デスクトップで使用されるデータストレージ、使用状況、およびセキュリティプラクティスについては、ホワイトペーパーを参照してください [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>デバイスのセキュリティ

Microsoft マネージド デスクトップは、すべての管理対象デバイスをセキュリティで保護し、次のサービスを使用して脅威を可能な限り早く検出します。

サービス | 説明
--- | ---
ウイルス対策 | Microsoft Defender AV がインストールおよび構成されている<br>Microsoft Defender AV の定義が最新の場合
フル ボリューム暗号化 |    Windows BitLocker は、Microsoft マネージド デスクトップ デバイス用のボリューム暗号化ソリューションです。<br><br>組織がサービスにオンボードされた後は、デバイスがスリープ モードのときにローカル データへの不正アクセスを防ぐため、TPM (組み込みのセキュリティ プラットフォーム モジュール) を使って Windows BitLocker を使用してデバイスが暗号化されます。 
監視 |    Microsoft Defender for Endpoint は、すべての Microsoft マネージド デスクトップ デバイスでセキュリティの脅威を監視するために使用されます。 Defender for Endpoint を使用すると、企業のお客様は、企業ネットワーク内の高度な脅威を検出、調査、および対応できます。 詳しくは [、「Microsoft Defender for Endpoint」をご覧ください。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
オペレーティング システムの更新プログラム |  Microsoft マネージド デスクトップ デバイスは、常に最新のセキュリティ更新プログラムで保護されます。
セキュア デバイス構成 |   Microsoft マネージド デスクトップは、Microsoft セキュリティベースラインを実装します。 詳しくは [、Windows セキュリティベースラインに関するページをご覧ください。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>ID およびアクセス管理

ID とアクセス管理は、企業の資産とビジネスに不可欠なデータを保護します。 Microsoft マネージド デスクトップは、Azure Active Directory (Azure AD) 管理対象 ID で安全に使用するようにデバイスを構成します。 Azure テナントで正確な情報を保持する責任は、お客様ADです。 

サービス | 説明
--- | ---
生体認証 |  Windows Hello を使用すると、ユーザーは顔または PIN を使用してサインインし、パスワードの忘れや盗難を難しくすることができます。 お客様は、ハイブリッド構成でこのサービスを使用するために必要なオンプレミスの Active Directory の前提条件を実装する責任があります。 詳しくは [、「Windows Hello」をご覧ください。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
標準ユーザーのアクセス許可 |  システムを保護し、セキュリティを高めるために、ユーザーには標準ユーザー権限が割り当てられます。 このアクセス許可は、Windows Autopilot の Out-of-Box Experience の一部として割り当てられます。



## <a name="network-security"></a>ネットワーク セキュリティ

お客様は、ネットワーク セキュリティに関する責任を負います。 

サービス | 説明
--- | ---
VPN | お客様は VPN インフラストラクチャを所有し、限られた企業リソースをイントラネットの外部に公開できます。<br><br>最小要件: Microsoft マネージド デスクトップには、Windows 10 互換でサポートされている VPN ソリューションが必要です。 組織で VPN ソリューションが必要な場合は、Windows 10 をサポートし、Intune を通じてパッケージ化して展開できる必要があります。 詳細については、ソフトウェア発行元にお問い合わせください。<br><br>推奨事項:<br>- Microsoft では、VPN プロファイルをプッシュするために Intune を介して簡単に展開できる最新の VPN ソリューションをお勧めします。 この方法では、常にオン、シームレス、信頼性、およびセキュリティで保護された方法で企業ネットワークにアクセスできます。 詳細については [、「[Intune での VPN 設定]」を参照してください](https://docs.microsoft.com/intune/vpn-settings-configure)。<br>- シック VPN クライアントまたは古い VPN クライアントは、ユーザー環境に影響を与える可能性がある Microsoft マネージド デスクトップを使用している間、Microsoft ではお勧めしません。<br>- パフォーマンスの問題を回避するために、送信 Web トラフィックは VPN を経由せずに直接インターネットに送信されます。<br>- VPN ではなく Azure Active Directory アプリ プロキシの使用をお勧めします。


## <a name="information-security"></a>情報セキュリティ

これらのオプションのサービスを構成して、企業の価値の高い資産を保護できます。 

サービス | 説明
--- | ---
データ回復  | デバイスのキー フォルダーに格納されている情報は、OneDrive for Business にバックアップされます。 Microsoft マネージド デスクトップは、OneDrive for Business と同期されていないデータに対して責任を負いません。 
Windows 情報保護 |    高レベルの情報セキュリティが必要な企業の場合は [、Windows 情報保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) と [Azure Information Protection をお勧めします](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

