---
title: iOS のエンドポイント向け Microsoft Defender の新機能
description: 以前のバージョンの Microsoft Defender for Endpoint on iOS の主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
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
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: d413bea8dc59bbfaa5b424bbbf421d7e12558fcb
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295399"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-ios"></a>iOS のエンドポイント向け Microsoft Defender の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="improved-experience-on-supervised-ios-devices"></a>監視対象の iOS デバイスでのエクスペリエンスの向上

Microsoft Defender for Endpoint on iOS では、これらの種類のデバイスでプラットフォームによって提供される管理機能の強化を考えると、監視対象の iOS/iPadOS デバイスに特化した機能が追加されました。 また、デバイスでローカル **VPN を設定せずに Web 保護を提供することもできます**。 これにより、エンドユーザーはシームレスなエクスペリエンスを実現しながら、フィッシングなどの Web ベースの攻撃から保護されます。 詳細については、この [ドキュメントを参照してください。](ios-install.md#complete-deployment-for-supervised-devices)

## <a name="threat-and-vulnerability-management"></a>脅威と脆弱性の管理

2022 年 1 月 25 日、Android と iOS の脅威と脆弱性の管理の一般提供を発表しました。 詳細については、 [techcommunity の投稿を参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)。

## <a name="1124210103"></a>1.1.24210103

- 監視対象デバイスでのインターネット接続の問題を解決しました。 詳細については、「Deploy [Defender for Endpoint on 登録済み iOS デバイス」を参照してください](ios-install.md)。
- バグ修正。

## <a name="1123250104"></a>1.1.23250104

- パフォーマンスの最適化 - このバージョンでバッテリーのパフォーマンスをテストし、フィードバックをお寄せください。
- **登録済み iOS** デバイスのオンボードゼロタッチ - このバージョンでは、Microsoft エンドポイント マネージャー (Intune) 経由で登録されたデバイスのゼロタッチ オンボードのプレビューが追加されました。 詳細については、セットアップと構成 [の詳細については](ios-install.md#zero-touch-onboarding-of-microsoft-defender-for-endpoint-preview) 、このドキュメントを参照してください。
- **プライバシーコントロール** - フィッシングアラートレポートのプライバシー制御を構成します。 詳細については、「 [Configure iOS features」を参照してください](ios-configure-features.md)。

## <a name="1123010101"></a>1.1.23010101

- バグ修正とパフォーマンスの向上 
  - このリリースでは、パフォーマンスの最適化が行われた。 このバージョンでバッテリーのパフォーマンスをテストし、フィードバックをお寄せください。

## <a name="1120240103"></a>1.1.20240103
- デバイス正常性カード - デバイス正常性カードは、保留中のソフトウェア更新プログラムについてエンド ユーザーに通知します。
- 操作性の強化 - エンド ユーザーは、MSDefender アプリ自体から Defender for Endpoint VPN を無効にできます。 この更新プログラムの前に、エンド ユーザーはアプリから VPN のみを無効設定でした。
- バグ修正。

## <a name="1120020101"></a>1.1.20020101
- UX の機能強化 - Microsoft Defender for Endpoint に新しい外観が追加されています。
- バグ修正。

## <a name="1117240101"></a>1.1.17240101
- Intune を介したモバイル アプリケーション管理 (MAM) のサポートは、通常、このバージョンで利用できます。 詳細については、「 [Microsoft Defender for Endpoint risk signals for your App protection policies」を参照してください。](https://techcommunity.microsoft.com/t5/intune-customer-success/microsoft-defender-for-endpoint-risk-signals-available-for-your/ba-p/2186322)
- **脱獄検出は** 一般に利用できます。 詳細については、「デバイス リスク信号 [に基づく条件付きアクセス ポリシーのセットアップ」を参照してください](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)。
- **登録されたデバイスの VPN プロファイル** の自動セットアップは、Microsoft エンドポイント マネージャー (Intune) 経由で一般に利用できます。 詳細については、「登録済み [iOS デバイスの自動セットアップ VPN プロファイル」を参照してください](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- バグ修正。

## <a name="1115140101"></a>1.1.15140101

- **脱獄検出は** プレビュー中です。 詳細については、「デバイス リスク信号 [に基づく条件付きアクセス ポリシーのセットアップ」を参照してください](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)。
- **VPN プロファイルの自動セットアップは、** 登録されたデバイスのプレビューで、アプリ (Intune) をMicrosoft エンドポイント マネージャーされます。 詳細については、「登録済み [iOS デバイスの自動セットアップ VPN プロファイル」を参照してください](ios-install.md#auto-onboarding-of-vpn-profile-simplified-onboarding)。
- Microsoft Defender ATP 製品名が、アプリ ストアの Microsoft Defender for Endpoint に更新されました。
- サインイン エクスペリエンスが向上しました。
- バグ修正。

## <a name="1115010101"></a>1.1.15010101

- このバージョンでは、iPadOS/iPadを発表しています。
- バグ修正。
