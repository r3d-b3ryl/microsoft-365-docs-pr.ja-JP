---
title: デバイス構成
description: Microsoft マネージドデスクトップデバイスに適用される既定のポリシーについて説明します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 93c7cca75f513008706b4a52b4bbc1bc033341aa
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830485"
---
# <a name="device-configuration"></a>デバイス構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Microsoft マネージドデスクトップの新しいデバイスがセットアップされている場合は、Microsoft マネージドデスクトップ用に最適化された適切な構成を備えていることを確認してください。 これには、オンボードプロセスの一部として設定される一連の既定のポリシーが含まれています。 競合を回避するには、これらのポリシーを変更しないようにします。 

デバイスは署名画像と共に到着し、最初のユーザーがログインしたときに Azure Active Directory ドメインに参加します。 必要なポリシーとアプリケーションがデバイスによって自動的にインストールされます。 IT の介入は必要ありません。

## <a name="why-mdm-over-group-policy"></a>グループポリシーによる MDM の理由

グループポリシーではなく、モバイルデバイス管理 (MDM) を使用する理由はいくつかあります。

- セキュリティ-MDM ポリシーの方が安全です。 グループポリシーは、MDM の id 管理 (Azure Active Directory) で最適に機能するように設計されたオンプレミスの id で最適に動作するように設計されています。
- 信頼性-MDM ポリシーにより、より信頼性の高いポリシーの展開が実現されます。 また、MDM 設定は、グループポリシーオブジェクト (GPO) ポリシーを上書きします。 Windows 10 version 1803 以降では、MDM 設定はグループポリシー値より優先されます。これにより、モダン管理への移行をお客様にサポートします。 
- Microsoft マネージドデスクトップビジョンとの連携-ポリシー展開についてのより包括的な監視を提供し、必要に応じて展開を一時停止/再開するための機能を使用して、ポリシーの変更を段階的にロールアウトするためのグループベースのアプローチをサポートします。

詳細については、「[モバイルデバイス管理](https://docs.microsoft.com/windows/client-management/mdm/)」を参照してください。 

## <a name="default-policies"></a>既定のポリシー

次の表に、デバイスのプロビジョニング時にすべての Microsoft マネージドデスクトップデバイスに適用される既定のポリシーを示します。 Microsoft managed desktop Operations Team で承認されていないすべての検出された変更は、Microsoft マネージドデスクトップで管理されるオブジェクトに戻されます。

ポリシー | 説明
--- | ---
セキュリティベースライン | MDM の[microsoft セキュリティベースライン](https://docs.microsoft.com/windows/device-security/windows-security-baselines)は、Microsoft マネージドデスクトップデバイスすべてに対して構成されています。 この基準は、業界標準の構成です。 これは一般にリリースされ、十分にテストされており、microsoft のセキュリティ担当者によって、モダンワークプレースで Microsoft の管理されたデスクトップデバイスとアプリが安全に保たれるようになっています。 <br><br>常に進化しているセキュリティ脅威の状況において脅威を軽減するために、Microsoft セキュリティベースラインが更新され、Windows 10 機能更新プログラムごとに Microsoft マネージドデスクトップデバイスに展開されます。<br><br>詳細については、「 [Windows 10 のセキュリティベースライン](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)」を参照してください。
Microsoft Managed デスクトップ推奨セキュリティテンプレート | ユーザーの利便性を最適化する、セキュリティベースラインに対する推奨される変更のセット。  これらの変更点につい[ては、「セキュリティ補遺](#security-addendum)」に記載されています。 補遺のポリシーへの更新は、必要に応じて実行されます。  
更新プログラムの展開 | Windows Update for Business を使用して、ソフトウェア更新プログラムの段階的な展開を行います。 IT 管理者は、展開グループポリシーの設定を変更することはできません。 グループベースの展開の詳細については、「[更新プログラムの処理方法](../working-with-managed-desktop/updates.md)」を参照してください。
診断データ | デバイスは、既知の商用識別子の下に拡張診断データを Microsoft に提供するように設定されます。 Microsoft マネージドデスクトップの一部として、IT 管理者はこれらの設定を変更できません。 一般的なデータ保護規則 (GDPR) 地域のお客様にとって、エンドユーザーは提供される診断データのレベルを下げることができますが、サービスが減少します。 たとえば、Microsoft マネージドデスクトップでは、パフォーマンスとセキュリティのニーズを満たすために、設定とポリシーを反復処理するために必要なデータを収集することはできません。 詳細については、「[組織で Windows 診断データを構成する](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)」を参照してください。
従量制課金接続 | 既定では、従量制課金接続 (LTE ネットワークなど) での更新はオフになっていますが、各ユーザーは **[設定 > 更新 > プログラム] の [詳細オプション]** でこの機能を個別に有効にすることができます。 すべてのユーザーが従量制課金接続での更新を有効にできるようにするには、[変更要求を送信](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support)します。これにより、すべてのデバイスに対してこの設定が有効になります。

 ## <a name="security-addendum"></a>セキュリティ補遺

 このセクションでは、[既定のポリシー](#default-policies)にリストされている標準の Microsoft 管理デスクトップポリシーに加えて展開されるポリシーの概要について説明します。 この構成は、金融サービスおよび規制の厳しい業界を念頭に置いて設計されており、ユーザーの生産性を維持しながら、最高のセキュリティを実現します。

 ### <a name="additional-security-policies"></a>その他のセキュリティポリシー

 これらのポリシーは、規制の厳しい業界のセキュリティを強化するために追加されています。 
 - **セキュリティの監視**: Microsoft [Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)を使用してデバイスを監視します。 脅威が検出された場合、Microsoft はお客様に通知し、デバイスを分離して、問題をリモートで修正します。 
 - **Powershell V2 を無効にする**: Microsoft は、2017年8月に powershell v2 を削除しました。 この機能は、Microsoft マネージドデスクトップのすべてのデバイスで無効になっています。 この変更の詳細については、「 [Windows PowerShell 2.0 の廃止](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)」を参照してください。
