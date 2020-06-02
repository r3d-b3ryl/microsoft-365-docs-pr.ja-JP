---
title: Microsoft マネージドデスクトップのセキュリティ
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 8bfd71c4a143dee54ae006c8c54d711a8785480f
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470491"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのセキュリティ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft マネージドデスクトップでは、管理されたデバイスとデータを保護するために、いくつかの Microsoft テクノロジを使用しています。 具体的には次のとおりです。 


- [デバイスセキュリティ](#device-security)– Microsoft マネージドデスクトップデバイスのセキュリティと保護
- [Id およびアクセス管理](#identity-and-access-management): Azure Active Directory id サービスを使用して、デバイスの安全な使用を管理する
- [ネットワークセキュリティ](#network-security)– VPN 情報と Microsoft Managed Desktop 推奨ソリューションと設定
- [情報セキュリティ](#information-security)–機密情報をさらに保護するためのオプションの利用可能なサービス 

Microsoft マネージドデスクトップで使用されるデータストレージ、使用方法、セキュリティプラクティスの詳細については、ホワイトペーパー「」をダウンロードしてください [https://aka.ms/mmd-data](https://aka.ms/mmd-data) 。


## <a name="device-security"></a>デバイスのセキュリティ

Microsoft マネージドデスクトップは、すべての管理対象デバイスをセキュリティ保護して保護し、次のサービスを使用してできるだけ早く脅威を検出します。

サービス | 説明
--- | ---
ウイルス対策 | Microsoft Defender AV がインストールされ、構成されている<br>Microsoft Defender の AV 定義が最新のものである
完全なボリューム暗号化 |    Windows BitLocker は、Microsoft マネージドデスクトップデバイス用のボリューム暗号化ソリューションです。<br><br>組織がサービスに利用されると、デバイスは Windows BitLocker を組み込み信頼プラットフォームモジュール (TPM) を使用して暗号化されます。これにより、デバイスがスリープモードまたはオフのときに、ローカルデータへの権限のないアクセスを防ぐことができます。 
監視 |    Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) は、Microsoft マネージドデスクトップデバイスすべてにわたるセキュリティ脅威監視に使用されます。 Microsoft Defender ATP を使用すると、企業のネットワークで高度な脅威を検出、調査、応答することができます。 詳細については、「 [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 」を参照してください。 
オペレーティングシステムの更新プログラム |  Microsoft マネージドデスクトップデバイスは、常に最新のセキュリティ更新プログラムでセキュリティ保護されています。
セキュリティで保護されたデバイス構成 |   Microsoft マネージドデスクトップは、Microsoft セキュリティベースラインを実装します。 詳細については、「 [Windows セキュリティベースライン](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)」を参照してください。



## <a name="identity-and-access-management"></a>ID およびアクセス管理

Id およびアクセス管理により、企業の資産とビジネス上の重要なデータが保護されます。 Microsoft マネージドデスクトップでは、Azure Active Directory (Azure AD) 管理 id との安全な使用を保証するようにデバイスが構成されています。 Azure AD テナントで正確な情報を維持することはお客様の責任です。 

サービス | 説明
--- | ---
バイオメトリクス認証 |  Windows Hello を使用すると、ユーザーは顔または PIN を使用してサインインすることができ、パスワードを忘れることがなくなります。 お客様は、ハイブリッド構成でこのサービスを使用するために、オンプレミスの Active Directory に必要な前提条件を実装する責任があります。 詳細については、「 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 」を参照してください。 
標準ユーザーアクセス許可 |  システムを保護し、より安全なものにするために、ユーザーには標準のユーザーアクセス許可が割り当てられます。 これは、Windows 自動操縦機能の一部として割り当てられます。



## <a name="network-security"></a>ネットワーク セキュリティ

お客様はネットワークセキュリティを担当しています。 

サービス | 説明
--- | ---
VPN | お客様は VPN インフラストラクチャを所有しており、制限された企業リソースをイントラネットの外部に公開することができます。<br><br>最小要件: Microsoft Managed Desktop には、Windows 10 互換およびサポートされている VPN ソリューションが必要です。 組織に VPN ソリューションが必要な場合は、Windows 10 をサポートし、Intune 経由でパッケージ化して展開する必要があります。 詳細については、ソフトウェアの発行元にお問い合わせください。<br><br>勧告<br>-Microsoft では、Intune を使用して VPN プロファイルをプッシュして簡単に展開できる先進の VPN ソリューションをお勧めします。 これにより、常に、シームレスで信頼性が高く、企業ネットワークにアクセスするための安全な方法が提供されます。 詳細については、「 [Intune の VPN 設定](https://docs.microsoft.com/intune/vpn-settings-configure)」を参照してください。<br>-サードユーザー環境に影響を与える可能性があるため、microsoft マネージドデスクトップの使用時に Microsoft は、太 VPN クライアントまたはレガシ VPN クライアントをお勧めしません。<br>-Microsoft では、パフォーマンスの問題を回避するために、送信 web トラフィックを VPN 経由で直接インターネットに移動することをお勧めします。<br>-Microsoft では、VPN の代わりに Azure Active Directory アプリプロキシを使用することをお勧めします。


## <a name="information-security"></a>情報セキュリティ

企業の価値の高い資産を保護するために、これらのオプションのサービスを構成できます。 

サービス | 説明
--- | ---
データの回復  | デバイス上の重要なフォルダーに格納されている情報は、OneDrive for Business にバックアップされます。 Microsoft マネージドデスクトップは、OneDrive for Business と同期されていないデータに対しては責任がありません。 
Windows 情報保護 |    高度なレベルの情報セキュリティが必要な企業では、 [Windows 情報保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)と[Azure information protection](https://www.microsoft.com/cloud-platform/azure-information-protection)をお勧めします。 

