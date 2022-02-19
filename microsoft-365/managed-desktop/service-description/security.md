---
title: Microsoft Managed Desktop のセキュリティ テクノロジ
description: デバイス セキュリティ、ID およびアクセス管理、ネットワーク セキュリティ、および情報セキュリティに使用されるテクノロジ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 7b5f99a6927fd87b1d75bde0dcc5e4fde1ff3a62
ms.sourcegitcommit: 966344e1aa442a4d10a0fb05f56badd38c833bb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909701"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop のセキュリティ テクノロジ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop は、いくつかの Microsoft テクノロジを使用して、管理対象デバイスとデータのセキュリティ保護に役立ちます。 さらに、Microsoft Managed Desktop Security Operations Center では、これらのテクノロジでさまざまな [プロセス](security-operations.md) を使用します。 特に次のような場合です。

| プロセス | 説明 |
| ------ | ------ |
| [デバイスのセキュリティ](#device-security)| Microsoft Managed Desktop デバイスのセキュリティと保護。 |
| [ID とアクセスの管理](#identity-and-access-management) | ID サービスによるデバイスの安全な使用Azure Active Directory管理します。 |
| [ネットワーク セキュリティ](#network-security)| VPN 情報と Microsoft Managed Desktop 推奨ソリューションと設定。 |
| [情報セキュリティ](#information-security)| 機密情報をさらに保護するためのオプションの利用可能なサービス。 |

Microsoft Managed Desktop で使用されるデータストレージ、使用状況、およびセキュリティプラクティスの詳細については、以下のホワイトペーパーを参照してください [https://aka.ms/mmd-data](https://aka.ms/mmd-data)。

## <a name="device-security"></a>デバイスのセキュリティ

Microsoft Managed Desktop では、すべての管理対象デバイスがセキュリティで保護され、次のサービスを使用して、可能な限り早期に脅威を検出します。

| サービス | 説明 |
| ----- | ----- |
| ウイルス対策 | Microsoft Defender ウイルス対策インストールおよび構成済み<br>Microsoft Defender ウイルス対策定義は最新です。 |
| ボリューム全体の暗号化 | Windows BitLocker は、Microsoft Managed Desktop デバイスのボリューム暗号化ソリューションです。<br><br>組織がサービスに登録すると、デバイスがスリープ モードまたはオフのときにローカル データへの不正アクセスを防止するために、Windows BitLocker と組み込みの信頼プラットフォーム モジュール (TPM) を使用してデバイスが暗号化されます。
| 監視 | Microsoft Defender for Endpoint は、すべての Microsoft Managed Desktop デバイスでセキュリティ脅威の監視に使用されます。 Defender for Endpoint を使用すると、企業のお客様は、企業ネットワーク内の高度な脅威を検出、調査、および対応できます。 詳細については、「 [Microsoft Defender for Endpoint」を参照してください。](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) |
| オペレーティング システムの更新 | Microsoft Managed Desktop デバイスは、常に最新のセキュリティ更新プログラムで保護されます。 |
| Secure Device Configuration | Microsoft Managed Desktop は、Microsoft セキュリティ ベースラインを実装します。 詳細については、「セキュリティベースライン[Windows参照してください。](/windows/security/threat-protection/windows-security-baselines)|

## <a name="identity-and-access-management"></a>ID およびアクセス管理

ID とアクセス管理は、企業の資産とビジネスクリティカルなデータを保護します。 Microsoft Managed Desktop は、デバイスを構成して、Azure Active Directory (Azure AD ID) で安全に使用します。 顧客の責任で、テナント内の正確な情報をAzure ADします。

| サービス | 説明 |
| ----- | ----- |
| 生体認証 | Windows Helloは、ユーザーが自分の顔または PIN を使用してサインインし、パスワードを忘れにくくしたり盗んだりすることを可能にしています。 お客様は、ハイブリッド構成でこのサービスを使用するために、オンプレミスの Active Directory に必要な前提条件を実装する責任があります。 詳細については、「Windows Hello[」を参照してください。](/windows-hardware/design/device-experiences/windows-hello) |
| 標準ユーザーのアクセス許可 | システムを保護し、セキュリティを高くするために、ユーザーには Standard User Permissions が割り当てられます。 このアクセス許可は、Autopilot Windowsエクスペリエンスの一部として割り当てられます。

## <a name="network-security"></a>ネットワーク セキュリティ

お客様はネットワーク セキュリティを担当します。

| サービス | 説明 |
| ----- | ----- |
| VPN | 制限された企業リソースをイントラネットの外部に公開できるよう、お客様は VPN インフラストラクチャを所有しています。<br><br>最小要件: Microsoft Managed Desktop には、互換性Windows 10サポートされている VPN ソリューションが必要です。 組織で VPN ソリューションが必要な場合は、Intune を介してパッケージ化Windows 10展開可能な VPN ソリューションをサポートする必要があります。 詳細については、ソフトウェア発行元にお問い合わせください。<br><br>推奨事項:<br><ul><li> Microsoft では、VPN プロファイルをプッシュするために Intune を介して簡単に展開できる最新の VPN ソリューションをお勧めします。 このアプローチは、企業ネットワークにアクセスするための常時オン、シームレス、信頼性、および安全な方法を提供します。 詳細については、「Intune の [VPN 設定」を参照してください](/intune/vpn-settings-configure)。</li><li>厚い VPN クライアント、または古い VPN クライアントは、ユーザー環境に影響を与える可能性がある Microsoft Managed Desktop を使用している間、Microsoft によって推奨されません。</li><li>パフォーマンスの問題を回避するために、送信 Web トラフィックは VPN を経由せずにインターネットに直接送信する必要があります。</li><li>理想的には、VPN ではなくアプリ プロキシAzure Active Directory使用をお勧めします。</li></ul>


## <a name="information-security"></a>情報セキュリティ

企業の価値の高い資産を保護するために、これらのオプション サービスを構成できます。

| サービス | 説明 |
| ----- | ----- |
| データ復旧 | デバイス上のキー フォルダーに格納されている情報は、OneDrive for Business。 Microsoft Managed Desktop は、データと同期されていないデータに対して責任を負OneDrive for Business。
| Windows 情報保護 | 高レベルの情報セキュリティが必要な企業の場合は、Windows [Azure Information Protection を](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)[使用することをお勧めします。](https://www.microsoft.com/cloud-platform/azure-information-protection)
