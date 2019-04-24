---
title: デバイス構成
description: Microsoft マネージドデスクトップデバイスに適用される既定のポリシーについて説明します。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a080c044939dfde223c231dfebdd248861d5f9f
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278626"
---
# <a name="device-configuration"></a>デバイス構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

microsoft マネージドデスクトップの新しいデバイスがプロビジョニングされている場合は、適切な構成である microsoft managed desktop 用に最適化されていることを確認してください。 これには、オンボードプロセスの一部として設定される一連の既定のポリシーが含まれています。 競合を回避するには、これらのポリシーを変更しないでください。 

デバイスは署名画像と共に到着し、最初のユーザーがログインしたときに Azure Active Directory ドメインに参加します。 必要なポリシーとアプリケーションがデバイスによって自動的にインストールされます。 IT の介入は必要ありません。

## <a name="why-mdm-over-group-policy"></a>グループポリシーによる MDM の理由

グループポリシーではなく、モバイルデバイス管理 (MDM) を使用する理由はいくつかあります。

- セキュリティ-MDM ポリシーの方がモダン world でセキュリティが強化されています。 グループポリシーは、MDM の id 管理 (Azure Active Directory) で最適に機能するように設計されたオンプレミスの id で最適に動作するように設計されています。
- 信頼性-MDM ポリシーにより、より信頼性の高いポリシーの展開が実現されます。 また、MDM 設定は、グループポリシーオブジェクト (GPO) ポリシーを上書きします。 Windows 10 version 1803 以降では、MDM 設定はグループポリシー値よりも優先されます。これにより、モダン管理への移行をお客様にサポートします。 
- Microsoft マネージドデスクトップビジョンとの連携-ポリシー展開についてのより包括的な監視を提供し、必要に応じて展開を一時停止/再開するための機能を使用して、ポリシーの変更を段階的にロールアウトするためのグループベースのアプローチをサポートします。

詳細については、「[モバイルデバイス管理](https://docs.microsoft.com/windows/client-management/mdm/)」を参照してください。 

## <a name="default-policies"></a>既定のポリシー

次の表に、デバイスのプロビジョニング時にすべての Microsoft マネージドデスクトップデバイスに適用される既定のポリシーを示します。 microsoft managed desktop Operations Team で承認されていないすべての検出された変更は、microsoft マネージドデスクトップで管理されるオブジェクトに戻されます。

ポリシー | 説明
--- | ---
セキュリティベースライン | MDM の[microsoft セキュリティベースライン](https://docs.microsoft.com/windows/device-security/windows-security-baselines)は、microsoft マネージドデスクトップデバイスすべてに対して構成されています。 この基準は、業界標準の構成です。 これは一般にリリースされ、十分にテストされており、microsoft のセキュリティ担当者によって、モダンワークプレースで microsoft の管理されたデスクトップデバイスとアプリが安全に保たれるようになっています。 <br><br>絶えず変化するセキュリティ脅威の状況において脅威を軽減するために、microsoft セキュリティベースラインが更新され、Windows 10 機能更新プログラムごとに microsoft マネージドデスクトップデバイスに展開されます。<br><br>詳細については、「 [Windows 10 のセキュリティベースライン](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)」を参照してください。
Microsoft Managed デスクトップ推奨セキュリティテンプレート | ユーザーの利便性を最適化する、セキュリティベースラインに対する推奨される変更のセット。  これらの変更点につい[ては、「セキュリティ補遺](#security-addendum)」に記載されています。 補遺のポリシーへの更新は、必要に応じて実行されます。  
デバイスのポリシー準拠 | これらのポリシーは、すべての Microsoft マネージドデスクトップデバイスに既定で構成されています。 次のいずれかのセキュリティ条件が満たされていない場合、デバイスは準拠していないと報告されます。<br>-デバイス上のデータを保護するために、BitLocker デバイス暗号化が有効になります。 詳細については、「 [Windows 10 での BitLocker デバイス暗号化の概要](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)」を参照してください。<br>-セキュアブートが有効で強制され、デバイスのファームウェアイメージを検証して実行することができます。 詳細については、「[セキュリティで保護されたブートとデバイスの暗号化の概要](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)」を参照してください。<br>-Microsoft Managed Desktop デバイスでは、ログインのパスワードが必要です。
更新プログラムの展開 | Windows Update for Business (WUfB) を使用して、ソフトウェア更新プログラムの段階的な展開を行います。 IT 管理者は、展開グループポリシーの設定を変更することはできません。 グループベースの展開の詳細については、「[更新プログラムの処理方法](../working-with-managed-desktop/updates.md)」を参照してください。
診断データ | デバイスは、既知の商用識別子の下に拡張診断データを Microsoft に提供するように設定されます。 Microsoft マネージドデスクトップの一部として、IT 管理者はこれらの設定を変更できません。 一般的なデータ保護規則 (GDPR) 地域のお客様にとって、エンドユーザーは提供される診断データのレベルを下げることができますが、サービスが減少します。 たとえば、Microsoft マネージドデスクトップでは、パフォーマンスとセキュリティのニーズを満たすために、設定とポリシーを反復処理するために必要なデータを収集することはできません。 詳細については、「[組織で Windows 診断データを構成する](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)」を参照してください。

 ## <a name="security-addendum"></a>セキュリティ補遺

 このセクションでは、標準の Microsoft 管理デスクトップポリシーに追加して展開されるポリシーの概要について説明します。 標準ポリシーは、[既定のポリシー](#default-policies)に一覧表示されます。 この構成は、金融サービスおよび規制の厳しい業界を対象として設計されており、ユーザーの生産性を維持しながら、最も安全な姿勢を最適化します。

 ### <a name="additional-security-policies"></a>その他のセキュリティポリシー

 これらのポリシーは、規制の厳しい業界のセキュリティを強化するために追加されます。 
 - **アプリの許可リスト**: Microsoft マネージドデスクトップデバイス上で実行するために、アプリが組織によって信頼されている必要があります。 これにより、ロックダウンされた環境が提供されます。 利用する必要があるアプリは、Microsoft Managed Desktop Operations Team に伝達する必要があります。 詳細については、「 [Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)」を参照してください。
 - **セキュリティの監視**: Microsoft は、 [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)を使用してデバイスを監視します。 脅威が検出された場合、Microsoft はお客様に通知し、デバイスを分離して、問題をリモートで修正します。 

