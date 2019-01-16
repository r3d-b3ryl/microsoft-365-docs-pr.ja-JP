---
title: デバイスの構成
description: Microsoft 管理デスクトップ デバイスに適用される既定のポリシーについて説明します。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365 サービス マニュアル
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869446"
---
# <a name="device-configuration"></a>デバイスの構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

新しい Microsoft 管理デスクトップ デバイスに準備されているが、右の構成では、Microsoft 管理されたデスクトップ用に最適化されていることを確認します。これには、登録プロセスの一部として設定されている既定のポリシーのセットが含まれます。競合を避けるためには、これらのポリシーを変更しないようにします。 

デバイスは、署名の画像を受信し、最初のユーザーがログインすると、Azure Active Directory ドメインに参加します。デバイスが自動的にインストール必要なポリシーとアプリケーションに必要な IT の介入なし。

## <a name="why-mdm-over-group-policy"></a>なぜ MDM をグループ ポリシー経由で

グループ ポリシーの代わりに、モバイル デバイス管理 (MDM) を使用するいくつかの理由があります。

- セキュリティの MDM のポリシーは、現代の世界でより安全です。グループ ポリシーは、MDM は、クラウド id 管理 (Azure Active Directory) で最適に動作するように設計されたときに、設置型の id を使用して最適に動作するよう設計されています。
- 信頼性の MDM のポリシーより信頼性の高いポリシーの展開を提供します。また、MDM の設定は、グループ ポリシー オブジェクト (GPO) のポリシーを上書きします。Windows 10、1803 のバージョンで始まる MDM の設定は優先順位をグループ ポリシーの値、最新の管理に移行するお客様をサポートします。 
- 管理されたデスクトップのマイクロソフトのビジョンに合わせて - ポリシーの展開より包括的な監視機能を提供し、停止/再開の展開が必要な場合に機能を段階的にロールアウト ポリシーを変更するグループ ベースのアプローチをサポートしています。

詳細については、[モバイル デバイスの管理](https://docs.microsoft.com/windows/client-management/mdm/)を参照してください。 

## <a name="default-policies"></a>既定のポリシー

このテーブルは、デバイスの提供処理中に Microsoft の管理されたデスクトップのすべてのデバイスに適用される既定のポリシーを強調表示します。検出されたすべての管理されたデスクトップの Microsoft によって管理されるオブジェクトに Microsoft 管理デスクトップ操作のチームは、未承認の変更を元に戻します。

ポリシー | 説明
--- | ---
セキュリティ基準 | MDM の[マイクロソフトのセキュリティの基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)は、管理されたデスクトップの Microsoft のすべてのデバイスの構成されます。この基準は、業界の標準的な構成です。公開されたら、十分にテストし、Microsoft 管理されたデスクトップのデバイスを保持するマイクロソフトのセキュリティ専門家が確認し、最新のワークプ レース内でアプリケーションをセキュリティで保護します。<br><br>常に進化するセキュリティ脅威の状況に脅威を軽減するには、マイクロソフトのセキュリティの基準による更新し、Windows 10 機能更新のたびに、Microsoft 管理デスクトップ デバイスに配備します。<br><br>詳細については、 [Windows の 10 のセキュリティ基準](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)を参照してください。
Microsoft 管理されたデスクトップは、セキュリティ テンプレートを推奨します。 | ユーザー エクスペリエンスを最適化するセキュリティ基準を推奨する変更のセット。 これらの変更は、[セキュリティの追加条項](#security-addendum)に記載されています。付属のポリシーの更新は、必要に応じてで発生します。  
デバイスのコンプライアンス | これらのポリシーは、管理されたデスクトップの Microsoft のすべてのデバイスの既定値で構成されます。セキュリティの次の条件のいずれかが満たされていない場合、非準拠デバイスが報告されます。<br>のデバイス上のデータを保護するために、BitLocker デバイスの暗号化を有効にします。詳細についてを参照してください[の概要の BitLocker デバイス暗号化 Windows 10 にします](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。<br>-セキュリティで保護されたブートが有効になり、実行することができます前に、デバイス上のファームウェア イメージを検証するために、適用されます。詳細についてを参照してください[ブートおよびデバイスのセキュリティで保護された暗号化の概要です](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)。<br>Microsoft 管理デスクトップ デバイスでは、ログインのパスワードが必要です。
更新プログラムの展開 | ビジネス (WUfB) の Windows Update を使用すると、ソフトウェアの更新の段階的な展開を実行できます。IT 管理者は、展開グループ ポリシーの設定を変更できません。グループ ベースの展開の詳細については、[更新プログラムを処理する方法](../working-with-managed-desktop/updates.md)を参照してください。
「遠隔測定」 | 商用既知の識別子の下にある、強化された診断データをマイクロソフトに提供するのには、デバイスが設定されます。Microsoft 管理されたデスクトップの一部として、IT 管理者はいないこれらの設定を変更できます。お客様の一般的なデータ保護規制 (GDPR) 地域では、エンド ・ ユーザー減らすことができます、提供されている診断データのレベルが、サービスを削減することがあります。たとえば、管理されたデスクトップの Microsoft されません設定とポリシーは、パフォーマンスとセキュリティのニーズに最適なサービスを提供する反復処理するために必要なデータを収集すること。詳細についてを参照してください[、組織の診断データを Windows を構成します](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。

 ## <a name="security-addendum"></a>付属のセキュリティ

 このセクションでは、標準的な Microsoft 管理デスクトップ ポリシーに追加導入されるポリシーについて説明します。[既定のポリシー](#default-policies)では、標準的なポリシーが一覧表示されます。この構成は、金融サービスおよび注意の規制の多い業界で設計されています: ユーザーの生産性を維持しながら、最も安全な態勢を最適化します。

 ### <a name="additional-security-policies"></a>追加のセキュリティ ポリシー

 規制の厳しい業界のセキュリティを強化するには、これらのポリシーが追加されます。 
 - **アプリケーションの一覧を許可する**: アプリケーションは、Microsoft 管理デスクトップ デバイス上で実行する組織によって信頼されている必要があります。これは、ロック ダウンした環境を提供します。Onboarded を使用する必要がある任意のアプリケーションは、Microsoft デスクトップ操作の管理チームに伝えなければなりません。詳細については、 [Windows Defender のデバイスの保護](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)を参照してください。
 - **セキュリティの監視**: マイクロソフトでは、[高度な脅威保護の Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)を使用してデバイスを監視します。マイクロソフトは、お客様に通知、脅威が検出される場合は、デバイスを特定し、リモートで問題を修正します。 

