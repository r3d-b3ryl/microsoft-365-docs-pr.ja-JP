---
title: Microsoft マネージド デスクトップのセキュリティ
description: ''
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869624"
---
# <a name="security-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのセキュリティ

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft 管理デスクトップでは、標準的な一連のポリシーが適用され、管理されたデスクトップのマイクロソフトのセキュリティで保護されたデバイス、ストアドの会社データ、ために多くのマイクロソフトのテクノロジを利用しています。以下に示す領域がさらに詳細については。  

- [データのセキュリティ](#data-security)- マイクロソフトの管理されたデスクトップとは、安全に保管によって収集されたデータの種類
- [デバイスのセキュリティ](#device-security): セキュリティと管理されたデスクトップの Microsoft デバイスの保護
- Azure Active Directory id のサービスを通じて、デバイスの[id およびアクセス管理](#identity-and-access-management): セキュリティで保護された管理を使用してください。
- [ネットワーク セキュリティ](#network-security): VPN 情報と管理されたデスクトップのマイクロソフトの推奨ソリューションと設定
- [情報セキュリティ](#information-security): さらに機密情報を保護するためのオプションの使用可能なサービス 

## <a name="data-security"></a>データ セキュリティ

(これによって、Microsoft 管理デスクトップ IT サービスの操作)、テナントのお客様から収集されたデータは、アメリカ合衆国でホストされている Microsoft のテナントに Azure の SQL データベースに格納されます。

詳細については、 [Microsoft Azure のセキュリティ](https://docs.microsoft.com/azure/security/azure-database-security-overview)を参照してください。

次のとおり、テナントから送信されるデータの種類。

- デバイスの更新プログラム、使用状況および信頼性データ
- アプリケーションの展開と信頼性のデータ
- 更新プログラムとセキュリティ ポリシーの配置のデータ
- デバイスに割り当てられているユーザー



## <a name="device-security"></a>デバイスのセキュリティ

Microsoft 管理されたデスクトップは、すべての管理対象デバイスは、セキュリティで保護されてと保護され、次のサービスを使用してできるだけ早い段階で脅威を検出を保証します。

サービス | 説明
--- | ---
ウイルス対策 | Windows Defender のウイルス対策のインストールし、構成<br>Windows Defender のウイルス対策定義が最新の状態
フル ボリューム暗号化 |    Windows BitLocker は、マイクロソフトの管理されたデスクトップのデバイスのボリューム暗号化ソリューションです。<br><br>組織がサービスに onboarded と、デバイスはデバイスがスリープ モードに切り替える場合は、ローカル データに不正アクセスを防止するのには Windows BitLocker と組み込み信頼プラットフォーム モジュール (TPM) を使用して暗号化されます。 
"Monitoring/監視" |    Windows Defender 高度な脅威保護 (Windows Defender の ATP) は、マイクロソフトの管理されたデスクトップのすべてのデバイス間でセキュリティの脅威を監視するために使用されます。Windows Defender の分析ツールにより、企業を検出、調査、および企業ネットワーク内の高度な脅威に対応します。詳細についてを参照してください[の高度な脅威保護の Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 。 
ソフトウェアの更新 |  管理されたデスクトップの Microsoft のデバイスは、常に最新のセキュリティ更新プログラムとセキュリティで保護されています。
セキュリティで保護されたデバイスの構成 |   Microsoft 管理されたデスクトップでは、マイクロソフトのセキュリティ ベースラインを実装します。詳細についてを参照してください[Windows セキュリティ ベースライン](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)。



## <a name="identity-and-access-management"></a>ID およびアクセス管理

アイデンティティおよびアクセス管理では、企業の資産とビジネス ・ クリティカルなデータを保護します。Microsoft 管理されたデスクトップでは、Azure Active Directory (AD の Azure) の使用をセキュリティで保護されたユーザーを管理することを確認するデバイスを構成します。Azure AD テナント内の正確な情報を維持するためにお客様の責任です。 

サービス | 説明
--- | ---
バイオ メトリック認証 |  Windows こんにちはでは、ユーザーが自分の顔や PIN、パスワードを忘れたり紛失したり、盗難が発生しにくくすることを使用してログインします。詳細についてを参照してください[Windows こんにちは](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)。
多要素認証 | Azure の多要素認証より緊密にも、セルフ サービス パスワード リセットとして、携帯電話を使用する認証のレベルを提供することによって管理されるデスクトップの Microsoft のサービスの重要な機能へのアクセスを制御します。 
標準ユーザーのアクセス許可 |  システムを保護し、セキュリティを強化、ユーザーが割り当てられます標準ユーザーのアクセス許可。これは、Windows の自動操縦装置の標準のエクスペリエンスの一部として割り当てられます。



## <a name="network-security"></a>ネットワークのセキュリティ

お客様は、ネットワークのセキュリティを担当します。 

サービス | 説明
--- | ---
VPN | お客様は、イントラネットの外部企業の限られたリソースを公開することを確認するのには、VPN インフラストラクチャを所有します。<br><br>最低限の条件: Microsoft の管理されたデスクトップには、Windows 10 互換性があり、サポートされている VPN ソリューションが必要です。組織では、VPN ソリューションを必要とする場合は、10 の Windows をサポートしており、パッケージ、および Intune によって展開する必要があります。詳細については、ソフトウェアの発行元に問い合わせてください。<br><br>に関する推奨事項:<br>マイクロソフトは、Intune によってプッシュ VPN プロファイルを簡単に展開されている最新の VPN ソリューションをお勧めします。これは、企業ネットワークにアクセスするのには、常時、シームレスな信頼性、およびセキュリティで保護された方法を提供します。詳細については、 [[Intune での VPN 設定]](https://docs.microsoft.com/intune/vpn-settings-configure)を参照してください。<br>-厚みの VPN クライアント、または従来の VPN クライアントでは、推奨されませんマイクロソフトによってエンドユーザーの環境に影響を与えることができます、マイクロソフトの管理されたデスクトップを使用しているときに。<br>マイクロソフトでは、発信の web トラフィックのパフォーマンスの問題を回避するのには VPN を経由せずにインターネットに直接にはお勧めします。<br>-理想的には、Azure Active ディレクトリのアプリケーション プロキシ、VPN ではなくの使用を推奨します。


## <a name="information-security"></a>情報セキュリティ

お客様は、企業の付加価値の高い資産を保護するためにこれらのオプション サービスを構成することができます。 

サービス | 説明
--- | ---
データ ・ リカバリ  | デバイス上のキーのフォルダーに格納された情報は、ビジネスの OneDrive にバックアップされます。Microsoft 管理されたデスクトップは、ビジネスのための OneDrive と同期されていないデータの責任ではありません。 
Windows 情報保護 |    [Windows の情報保護](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)をお勧め高いレベルの情報セキュリティを必要とする企業と[Azure 情報保護します。](https://www.microsoft.com/cloud-platform/azure-information-protection)。 

