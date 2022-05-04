---
title: iOS でのMicrosoft Defender for Endpointの新機能
description: iOS での以前のバージョンのMicrosoft Defender for Endpointの主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: sunasing
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 7f3a687eb365813192948e48514bf7384cc584d0
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188207"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-ios"></a>iOS でのMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


## <a name="integration-with-tunnel"></a>Tunnelとの統合
iOS のMicrosoft Defender for Endpointは、1 つのアプリでセキュリティと接続を有効にする VPN ゲートウェイ ソリューションである Microsoft Tunnel と統合できるようになりました。  Tunnelとの統合により、1 つのアプリだけで iOS でシンプルで安全な VPN エクスペリエンスが提供されます。 この機能は、以前は Android でのみ使用できます。 詳細については、[こちらにある techcommunity の投稿を参照してください](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995)。

## <a name="improved-experience-on-supervised-ios-devices"></a>監視対象の iOS デバイスでのエクスペリエンスの向上

iOS 上のMicrosoft Defender for Endpointでは、このような種類のデバイスでプラットフォームによって提供される管理機能が強化されたため、監視対象の iOS/iPadOS デバイスに特化した機能が追加されました。 **また、デバイスにローカル VPN を設定せずに** Web Protection を提供することもできます。 これにより、エンド ユーザーはシームレスなエクスペリエンスを得られますが、フィッシングやその他の Web ベースの攻撃から保護されます。 詳細については、 [このドキュメントを参照してください](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-app-store"></a>Microsoft Defender for Endpointがアプリ ストアに Microsoft Defender になりました

Microsoft Defender for Endpointは、アプリ ストアで **Microsoft Defender** として使用できるようになりました。 この更新プログラムを使用すると、 **アプリは米国リージョンのコンシューマー** 向けのプレビューとして利用できるようになります。 職場または個人アカウントでアプリにログインする方法に基づいて、Microsoft Defender for Endpointの機能や個人向けの Microsoft Defender の機能にアクセスできます。 詳細については、 [このブログ](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals)を参照してください。

## <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

2022 年 1 月 25 日に、Android と iOS での脅威と脆弱性の管理の一般公開が発表されました。 詳細については、 [こちらにある techcommunity の投稿](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)を参照してください。


## <a name="1128250101"></a>1.1.28250101
- **Tunnelとの統合** - iOS 上のMicrosoft Defender for Endpointは、1 つのアプリでセキュリティと接続を有効にする VPN ゲートウェイ ソリューションである Microsoft Tunnel と統合できるようになりました。 詳細については、「[Microsft Tunnel概要」を参照してください](/mem/intune/protect/microsoft-tunnel-overview)。
- Microsoft エンドポイント マネージャー (Intune) を通じて登録 **された登録済み iOS デバイスのゼロタッチ オンボード** は一般公開されています。 詳細については、「[Microsoft Defender for Endpointのゼロ タッチ オンボード](/microsoft-365/security/defender-endpoint/ios-install#zero-touch-onboarding-of-microsoft-defender-for-endpoint)」を参照してください。
- バグ修正。


## <a name="1124210103"></a>1.1.24210103

- 監視対象デバイスでのインターネット接続の問題を解決しました。 詳細については、「 [登録済みの iOS デバイスに Defender for Endpoint を展開する」を参照してください](ios-install.md)。
- バグ修正。

## <a name="1123250104"></a>1.1.23250104

- パフォーマンスの最適化 - このバージョンでバッテリのパフォーマンスをテストし、フィードバックをお知らせください。
- **登録済みの iOS デバイスのゼロタッチ オンボード** - このバージョンでは、Microsoft エンドポイント マネージャー (Intune) を通じて登録されたデバイスのゼロタッチ オンボードのプレビューが追加されました。 詳細については、セットアップと構成の詳細については、この [ドキュメント](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint) を参照してください。
- **プライバシー制御** - フィッシング アラート レポートのプライバシー 制御を構成します。 詳細については、「 [iOS 機能の構成」を](ios-configure-features.md)参照してください。

## <a name="1123010101"></a>1.1.23010101

- バグの修正とパフォーマンスの向上 
  - パフォーマンスの最適化は、このリリースで行われました。 このバージョンでバッテリのパフォーマンスをテストし、フィードバックをお知らせください。

## <a name="1120240103"></a>1.1.20240103
- デバイス正常性カード - デバイス正常性カードは、保留中のソフトウェア更新プログラムについてエンド ユーザーに通知します。
- 使いやすさの強化 - エンド ユーザーは、MSDefender アプリ自体から Defender for Endpoint VPN を無効にできるようになりました。 この更新プログラムの前に、エンド ユーザーは、設定 アプリからのみ VPN を無効にする必要がありました。
- バグ修正。

## <a name="1120020101"></a>1.1.20020101
- UX の機能強化 - Microsoft Defender for Endpointに新しい外観が追加されました。
- バグ修正。

## <a name="1117240101"></a>1.1.17240101
- Intuneを介したモバイル アプリケーション管理 (MAM) のサポートは、このバージョンで一般公開されています。 詳細については、[アプリ保護 ポリシーで使用できるリスクシグナルMicrosoft Defender for Endpoint](https://techcommunity.microsoft.com/t5/intune-customer-success/microsoft-defender-for-endpoint-risk-signals-available-for-your/ba-p/2186322)を参照してください
- **脱獄検出** は一般提供されています。 詳細については、「 [デバイス リスク信号に基づいて条件付きアクセス ポリシーを設定する](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)」を参照してください。
- Microsoft エンドポイント マネージャー (Intune) を介して登録されたデバイスの **VPN プロファイルの自動セットアップ** が一般公開されています。 詳細については、「 [登録済みの iOS デバイスの VPN プロファイルの自動セットアップ」を参照してください](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- バグ修正。

## <a name="1115140101"></a>1.1.15140101

- **脱獄の検出** はプレビュー段階です。 詳細については、「 [デバイス リスク信号に基づいて条件付きアクセス ポリシーを設定する](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)」を参照してください。
- **VPN プロファイルの自動セットアップ** は、Microsoft エンドポイント マネージャー (Intune) を介して登録されたデバイスのプレビュー段階にあります。 詳細については、「 [登録済みの iOS デバイスの VPN プロファイルの自動セットアップ」を参照してください](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- Microsoft Defender ATP の製品名が、アプリ ストア内のMicrosoft Defender for Endpointに更新されました。
- サインイン エクスペリエンスが向上しました。
- バグ修正。

## <a name="1115010101"></a>1.1.15010101

- このバージョンでは、iPadOS/iPad デバイスのサポートを発表します。
- バグ修正。
