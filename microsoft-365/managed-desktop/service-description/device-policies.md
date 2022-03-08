---
title: デバイス構成
description: Microsoft Managed Desktop デバイスに適用される既定のポリシーについて説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 19acff97a1541dcf6151b531696cf373e604371f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327855"
---
# <a name="device-configuration"></a>デバイス構成

<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

新しい Microsoft Managed Desktop デバイスがセットアップされている場合は、構成が Microsoft マネージ デスクトップに最適化されています。

構成には、オンボーディング プロセスの一部として設定される一連の既定のポリシーが含まれています。 これらのポリシーは、可能な限りモバイル デバイス管理 (MDM) を使用して配信されます。 詳細については、「Mobile [Device Management」を参照してください](/windows/client-management/mdm/)。

>[!NOTE]
>競合を回避するには、これらのポリシーを変更しないようにしてください。

デバイスは署名イメージで到着し、最初のユーザーがサインインAzure Active Directoryドメインに参加します。 デバイスは、IT 担当者の介入なしに、必要なポリシーとアプリケーションを自動的にインストールします。

## <a name="default-policies"></a>既定のポリシー

次の表では、デバイスのプロビジョニング中にすべての Microsoft Managed Desktop デバイスに適用される既定のポリシーについて説明します。 Microsoft Managed Desktop Operations Team によって承認され、Microsoft Managed Desktop によって管理されていないオブジェクトに対して検出された変更はすべて元に戻されます。

| ポリシー | 説明
| ----- | ----- |
| セキュリティベースライン | [モバイル デバイス管理の](/windows/device-security/windows-security-baselines) Microsoft セキュリティ 基準は、すべての Microsoft 管理デスクトップ デバイスに対して構成されます。 この基準は業界標準の構成です。 Microsoft Managed Desktop デバイスとアプリを最新の職場で安全に保つために、Microsoft のセキュリティ専門家によって公開、よくテスト、およびレビューされています。 <br><br>絶えず進化し続けるセキュリティ脅威の状況での脅威を軽減するために、Microsoft のセキュリティ ベースラインが更新され、各機能更新プログラムを使用して Microsoft Managed Desktop デバイスWindows 10展開されます。<br><br>詳細については、「セキュリティベースライン[Windows参照してください](/windows/security/threat-protection/windows-security-baselines)。
| Microsoft Managed Desktop 推奨セキュリティ テンプレート | このテンプレートは、ユーザー エクスペリエンスを最適化するセキュリティ 基準に対する推奨される変更のセットです。 これらの変更は、Security [Addendum に記載されています](#security-addendum)。 ポリシーの追加に対する更新は、必要に応じて行われます。  
| 展開の更新 | ソフトウェア更新Windows段階的な展開を実行するには、「Update for Business」を使用します。 IT 管理者は、展開グループ ポリシーの設定を変更できない。 グループ ベースの展開の詳細については、「Microsoft Managed Desktop での更新プログラムの [処理方法」を参照してください](updates.md)。
| メーター接続 | 既定では、メーター接続 (LTE ネットワークなど) に対する更新は無効になっています。 しかし、各ユーザーは、この設定を個別にオンにできます。この設定は、設定更新プログラム、次に [詳細設定 **] に移動します**。 <br><br>すべてのユーザーがメーター接続を使用して更新を有効にしたい場合は[](../working-with-managed-desktop/admin-support.md)、すべてのデバイスに対してこの設定を有効にする変更要求を送信します。
| デバイスのコンプライアンス | これらのポリシーは、すべての Microsoft 管理デスクトップ デバイスに対して構成されます。 デバイスが必要なセキュリティ構成から離れた場合、デバイスは非準拠として報告されます。

## <a name="windows-diagnostic-data"></a>Windows 診断データ

 既知の商用識別子の下で、Microsoft に拡張診断データを提供するためにデバイスが設定されます。 Microsoft Managed Desktop の一部として、IT 管理者はこれらの設定を変更できます。

一般データ保護規則 (GDPR) 地域のお客様の場合、ユーザーは提供される診断データのレベルを下げできますが、サービスが低下します。 たとえば、Microsoft Managed Desktop は、パフォーマンスとセキュリティのニーズに最適なサービスを提供するために、設定とポリシーを反復処理するために必要なデータを収集できません。 詳細については、「組織の[診断データWindows構成する」を参照してください。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>セキュリティの追加

 このセクションでは、「既定のポリシー」に記載されている標準の Microsoft Managed Desktop ポリシーに加えて展開されるポリシーの概要 [を説明します](#default-policies)。 この構成は、金融サービスと規制の厳しい業界を念頭に置いて設計されており、ユーザーの生産性を維持しながら、最高のセキュリティのために最適化されています。

### <a name="additional-security-policies"></a>追加のセキュリティ ポリシー

 これらのポリシーは、規制の厳しい業界のセキュリティを強化するために追加されます。

| ポリシー | 説明 |
| ----- | ----- |
|セキュリティ監視 | Microsoft は、Microsoft [Defender for Endpoint を使用してデバイスを監視します](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 脅威が検出された場合、Microsoft は顧客に通知し、デバイスを分離し、リモートで問題を修正します。 |
 | PowerShell V2 を無効にする | Microsoft は 2017 年 8 月に PowerShell V2 を削除しました。<br><br>この機能は、すべての Microsoft 管理デスクトップ デバイスで無効になっています。 この変更の詳細については、「Windows PowerShell [2.0 非推奨」を参照してください](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。 |
