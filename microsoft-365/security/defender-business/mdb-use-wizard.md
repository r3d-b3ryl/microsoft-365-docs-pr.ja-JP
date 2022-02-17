---
title: ウィザードを使用して Microsoft Defender for Business をセットアップする (プレビュー)
description: Defender for Business には、ウィザードのようなセットアップと構成プロセスが含まれます。 ウィザードを使用して時間と労力を節約します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/16/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 26bf8e46ba79094f74fe542f932921d4f1c2a50d
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879134"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business-preview"></a>ウィザードを使用して Microsoft Defender for Business をセットアップする (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐[](https://aka.ms/mdb-preview)々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは最初の一連 [のシナリオで](mdb-tutorials.md#try-these-preview-scenarios)起動し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) は、初期セットアップと構成のためのウィザードのようなエクスペリエンスを使用して、中小企業の時間と労力を節約するように設計されています。 この記事では、ウィザードの手順と、Defender for Business を手動で設定および構成するためのオプションについて説明します。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Defender for Business をセットアップするウィザードのホーム画面のスクリーンショット。":::

## <a name="overview-of-the-wizard"></a>ウィザードの概要

ウィザードは、Defender for Business を迅速かつ効率的にセットアップおよび構成するのに役立つ設計です。 ウィザードでは、次の手順を実行します。

1. **ユーザーのアクセス許可を割り当てる**。 この手順では、セキュリティ チームにポータル () へのアクセス権をMicrosoft 365 Defenderします[https://security.microsoft.com](https://security.microsoft.com)。 ポータル アクセスは、特定のアクセス許可を示す役割を通じて付与されます。 [役割とアクセス許可について詳しくは、次のページをご覧ください](mdb-roles-permissions.md)。

   - グローバル管理者は、テナント全体のすべての設定を表示およびMicrosoft 365できます。 
   - セキュリティ管理者は、セキュリティ設定を表示および編集できます。 
   - セキュリティ リーダーは、レポート内の情報のみを表示できます。 

2. **電子メール通知を設定します**。 この手順では、検出された脆弱性または新しいアラートが発生した場合に電子メール通知を受信するユーザーを決定します。 電子メール通知は、セキュリティ チームがデスクから離れていなくても、情報を保持するのに役立ちます。 [電子メール通知の詳細については、次の情報を参照してください](mdb-email-notifications.md)。 

3. **デバイスのオンボードと構成Windowsします**。 この手順では、組織のデバイスを Defender for Business Windowsすぐにオンボードできます。 デバイスのオンボードは、1 日目からデバイスを保護するのに役立ちます。 

   - Microsoft Intune (Microsoft エンドポイント マネージャー の一部) を既に使用している場合に、組織にデバイスが エンドポイント マネージャー に登録されている場合は、登録されている Windows デバイスの一部またはすべてに対して自動オンボーディングを使用するかどうかを確認するメッセージが表示されます。 自動オンボーディングでは、エンドポイント マネージャーと Defender for Business の間の接続をセットアップし、Windowsデバイスを Defender for Business にシームレスにオンボードします。

   - エンドポイント マネージャー をまだ使用していない場合、または エンドポイント マネージャー に登録されている Windows 以外のデバイスがある場合は、手動で Defender for Business (プレビュー) にデバイスをオンボードできます。 

   - 「 [オンボード デバイスから Microsoft Defender for Business (プレビュー)」を参照してください](mdb-onboard-devices.md)。
   
4. **セキュリティ ポリシーを構成します**。 Defender for Business には、組織のデバイスに適用できる既定のセキュリティ ポリシーが含まれています。 これらの既定のポリシーは推奨設定を使用し、デバイスに強力な保護を提供するように設計されています。 ただし、必要に合わせ、独自のセキュリティ ポリシーを作成できます。 また、セキュリティ ポリシーを既に使用しているエンドポイント マネージャー、セキュリティ ポリシーの管理に引き続き使用できます。 

   - [簡略化された構成の詳細については、以下を参照してください](mdb-simplified-configuration.md)。
   - [セキュリティ ポリシーとデバイスを管理する場所を選択します](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>ウィザードを使用しない場合は、どうなるでしょうか。

ウィザードを使用しない場合、またはセットアップ プロセスが完了する前にウィザードを終了した場合でも、セットアップと構成プロセスを独自に完了できます。 手順 [については、「Microsoft Defender for Business (プレビュー)](mdb-setup-configuration.md) のセットアップと構成」を参照してください。

## <a name="next-steps"></a>次の手順

- [ポータルの使用Microsoft 365 Defenderする](mdb-get-started.md)

- [[脅威の管理] &のダッシュボードを使用する](mdb-view-tvm-dashboard.md)