---
title: デバイス構成
description: Microsoft マネージド デスクトップ デバイスに適用される既定のポリシーについて説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840333"
---
# <a name="device-configuration"></a>デバイス構成


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

新しい Microsoft マネージド デスクトップ デバイスがセットアップされている場合は、Microsoft マネージド デスクトップ用に最適化された適切な構成を持つ必要があります。 この構成には、オンボーディング プロセスの一部として設定される一連の既定のポリシーが含まれます。 これらのポリシーは、可能な限りモバイル デバイス管理 (MDM) を使用して配信されます。 詳細については、「モバイル デバイス管理 [」を参照してください](https://docs.microsoft.com/windows/client-management/mdm/)。 

>[!NOTE]
>競合を回避するために、これらのポリシーを変更しないようにしてください。

デバイスは署名イメージと一緒に到着し、最初のユーザーがサインインすると Azure Active Directory ドメインに参加します。 デバイスは、IT 担当者の介入なしに、必要なポリシーとアプリケーションを自動的にインストールします。

## <a name="default-policies"></a>既定のポリシー

次の表は、デバイスのプロビジョニング中にすべての Microsoft マネージド デスクトップ デバイスに適用される既定のポリシーを示しています。 Microsoft マネージド デスクトップ操作チームによって承認されていない、Microsoft マネージド デスクトップによって管理されるオブジェクトに対する検出された変更はすべて元に戻されます。

ポリシー | 説明
--- | ---
セキュリティベースライン | [MDM 用の Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) セキュリティ ベースラインは、すべての Microsoft マネージド デスクトップ デバイスに対して構成されます。 このベースラインは業界標準の構成です。 最新の職場で Microsoft マネージド デスクトップ デバイスとアプリのセキュリティを維持するために、Microsoft セキュリティの専門家によって一般にリリースされ、十分にテストされ、レビューされています。 <br><br>絶えず進化するセキュリティの脅威の状況で脅威を軽減するために、Microsoft のセキュリティ基本計画が更新され、各 Windows 10 機能更新プログラムを使用して Microsoft マネージド デスクトップ デバイスに展開されます。<br><br>詳しくは [、Windows セキュリティベースラインに関するページをご覧ください](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)。
Microsoft マネージド デスクトップの推奨セキュリティ テンプレート | ユーザー エクスペリエンスを最適化するセキュリティベースラインの推奨される変更のセット。  これらの変更は、セキュリティ [に関する追加文書に記載されています](#security-addendum)。 ポリシーの追加処理の更新は、必要に応じて行われます。  
展開を更新する | Windows Update for Business を使用して、ソフトウェア更新プログラムの段階的な展開を実行します。 IT 管理者は、展開グループ ポリシーの設定を変更できない。 グループ ベースの展開の詳細については、「Microsoft マネージド デスクトップでの更新プログラムの処理方法」 [を参照してください](updates.md)。
メートル接続 | 既定では、(LTE ネットワークなどの) メーター接続を使用した更新はオフになっていますが、各ユーザーは[設定] > [更新プログラム] > [詳細] オプションでこの機能を個別に有効に **できます**。 すべてのユーザーに対して、メートル制接続を使用した更新を有効[](../working-with-managed-desktop/admin-support.md)にする場合は、すべてのデバイスでこの設定をオンにする変更要求を送信します。
| デバイスのポリシー準拠 | これらのポリシーは、すべての Microsoft マネージド デスクトップ デバイスに対して構成されます。 デバイスは、必要なセキュリティ構成から外れた場合に非準拠として報告されます。

## <a name="windows-diagnostic-data"></a>Windows 診断データ

 デバイスは、既知の商用識別子の下で拡張診断データを Microsoft に提供するために設定されます。 Microsoft マネージド デスクトップの一部として、IT 管理者はこれらの設定を変更できません。 一般データ保護規則 (GDPR) 地域のお客様の場合、ユーザーは提供される診断データのレベルを下げできますが、サービスが減少します。 たとえば、Microsoft マネージド デスクトップでは、パフォーマンスとセキュリティのニーズに最適に対応するために設定とポリシーを反復処理するために必要なデータを収集できません。 詳細については、「組織内の Windows 診断 [データを構成する」を参照してください。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>セキュリティに関する追加

 このセクションでは、既定のポリシーに記載されている標準の Microsoft マネージド デスクトップ ポリシーに加えて展開されるポリシーの概要 [を示します](#default-policies)。 この構成は、金融サービスと厳しく規制された業界を念頭に置いて設計されており、ユーザーの生産性を維持しながら最高のセキュリティを実現するように最適化されています。

 ### <a name="additional-security-policies"></a>追加のセキュリティ ポリシー

 これらのポリシーは、厳しく規制された業界のセキュリティを強化するために追加されています。 
 - **セキュリティ監視**: Microsoft は、エンドポイント用 Microsoft Defender を [使用してデバイスを監視します](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。 脅威が検出された場合、Microsoft はユーザーに通知し、デバイスを分離して、問題をリモートで修正します。 
 - **PowerShell V2 を無効** にする : Microsoft は 2017 年 8 月に PowerShell V2 を削除しました。 この機能は、すべての Microsoft マネージド デスクトップ デバイスで無効になっています。 この変更の詳細については、「Windows PowerShell [2.0 Deprecation」を参照してください](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。
