---
title: デバイス構成
description: デバイスに適用される既定のポリシー Microsoft マネージド デスクトップします。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ec545a54988c2634c651ec07084c005467afd565
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210151"
---
# <a name="device-configuration"></a>デバイス構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

新しいMicrosoft マネージド デスクトップデバイスがセットアップされている場合は、デバイスの構成が適切に最適化Microsoft マネージド デスクトップ。 この構成には、オンボーディング プロセスの一部として設定される一連の既定のポリシーが含まれています。 これらのポリシーは、可能な限りモバイル デバイス管理 (MDM) を使用して配信されます。 詳細については、「Mobile [Device Management」を参照してください](/windows/client-management/mdm/)。 

>[!NOTE]
>競合を回避するには、これらのポリシーを変更しないようにしてください。

デバイスは署名イメージで到着し、最初のユーザーがサインインAzure Active Directoryドメインに参加します。 デバイスは、IT 担当者の介入なしに、必要なポリシーとアプリケーションを自動的にインストールします。

## <a name="default-policies"></a>既定のポリシー

次の表は、デバイスのプロビジョニング中にすべてのデバイスに適用Microsoft マネージド デスクトップポリシーを示しています。 ユーザーが管理するオブジェクトに対して、Microsoft マネージド デスクトップチームによって承認されていない検出された変更はすべて元に戻Microsoft マネージド デスクトップされます。

ポリシー | 説明
--- | ---
セキュリティベースライン | [MDM の Microsoft セキュリティ 基準](/windows/device-security/windows-security-baselines)は、すべてのデバイスにMicrosoft マネージド デスクトップされます。 この基準は業界標準の構成です。 公開され、十分にテストされ、Microsoft のセキュリティ専門家によってレビューされ、最新の職場で Microsoft マネージド デスクトップデバイスとアプリのセキュリティを維持しています。 <br><br>絶えず進化し続けるセキュリティ脅威の状況での脅威を軽減するために、Microsoft のセキュリティ ベースラインが更新され、各機能更新プログラムを使用して Microsoft マネージド デスクトップ デバイスWindows 10展開されます。<br><br>詳細については、「セキュリティ ベースライン[のWindowsを参照してください](/windows/security/threat-protection/windows-security-baselines)。
Microsoft マネージド デスクトップ推奨されるセキュリティ テンプレート | ユーザー エクスペリエンスを最適化するセキュリティ 基準に対する推奨される変更のセット。  これらの変更は、Security [Addendum に記載されています](#security-addendum)。 ポリシーの追加に対する更新は、必要に応じて行われます。  
展開の更新 | ソフトウェア更新Windows段階的な展開を実行するには、「Update for Business」を使用します。 IT 管理者は、展開グループ ポリシーの設定を変更できない。 グループ ベースの展開の詳細については、「[更新](updates.md)プログラムの処理方法」を参照Microsoft マネージド デスクトップ。
メーター接続 | 既定では、メーター接続 (LTE ネットワークなど) での更新は無効になっていますが、各ユーザーは 設定 > Updates > Advanced オプションでこの機能を個別 **に有効にできます**。 すべてのユーザーがメーター接続を使用して更新を有効にしたい場合は[](../working-with-managed-desktop/admin-support.md)、すべてのデバイスに対してこの設定を有効にする変更要求を送信します。
| デバイスのコンプライアンス | これらのポリシーは、すべてのデバイスにMicrosoft マネージド デスクトップされます。 デバイスが必要なセキュリティ構成から離れた場合、デバイスは非準拠として報告されます。

## <a name="windows-diagnostic-data"></a>Windows 診断データ

 既知の商用識別子の下で、Microsoft に拡張診断データを提供するためにデバイスが設定されます。 IT 管理者は、Microsoft マネージド デスクトップ設定を変更できません。 一般データ保護規則 (GDPR) 地域のお客様の場合、ユーザーは提供される診断データのレベルを下げできますが、サービスが低下します。 たとえば、Microsoft マネージド デスクトップとセキュリティのニーズに最適なサービスを提供するために、設定とポリシーを反復処理するために必要なデータを収集できません。 詳細については、「組織の[診断データWindows構成する」を参照してください。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>セキュリティの追加

 このセクションでは、「既定のポリシー」に記載されている標準のポリシーに加えてMicrosoft マネージド デスクトップポリシーの概要[を説明します](#default-policies)。 この構成は、金融サービスと規制の厳しい業界を念頭に置いて設計されており、ユーザーの生産性を維持しながら、最高のセキュリティを最適化します。

 ### <a name="additional-security-policies"></a>追加のセキュリティ ポリシー

 これらのポリシーは、規制の厳しい業界のセキュリティを強化するために追加されています。 
 - **セキュリティ監視**: Microsoft は、Microsoft [Defender for Endpoint を使用してデバイスを監視します](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 脅威が検出された場合、Microsoft は顧客に通知し、デバイスを分離し、リモートで問題を修正します。 
 - **PowerShell V2 を無効** にする : Microsoft は 2017 年 8 月に PowerShell V2 を削除しました。 この機能は、すべてのデバイスでMicrosoft マネージド デスクトップされています。 この変更の詳細については、「Windows PowerShell [2.0 非推奨」を参照してください](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。