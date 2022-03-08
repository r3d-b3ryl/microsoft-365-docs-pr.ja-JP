---
title: ウィザードを使用して Microsoft Defender for Business をセットアップする
description: Defender for Business には、ウィザードのようなセットアップと構成プロセスが含まれます。 ウィザードを使用して時間と労力を節約します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/02/2022
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
ms.openlocfilehash: 98660e437463a79ce263edd29f2cd01725d19762
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322927"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business"></a>ウィザードを使用して Microsoft Defender for Business をセットアップする

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business は、初期セットアップと構成のためのウィザードのようなエクスペリエンスを使用して、中小企業の時間と労力を節約するように設計されています。 この記事では、ウィザードの手順と、Defender for Business を手動で設定および構成するためのオプションについて説明します。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Defender for Business をセットアップするウィザードのホーム画面のスクリーンショット。":::

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="overview-of-the-wizard"></a>ウィザードの概要

ウィザードは、Defender for Business を迅速かつ効率的にセットアップおよび構成するのに役立つ設計です。 ウィザードでは、次の手順を実行します。

1. **ユーザーのアクセス許可を割り当てる**。 この手順では、セキュリティ チームにポータル () へのアクセス権Microsoft 365 Defenderします[https://security.microsoft.com](https://security.microsoft.com)。 ポータル アクセスは、特定のアクセス許可を示す役割を通じて付与されます。 [役割とアクセス許可について詳しくは、次のページをご覧ください](mdb-roles-permissions.md)。

   - グローバル管理者は、テナント全体のすべての設定を表示およびMicrosoft 365できます。 
   - セキュリティ管理者は、セキュリティ設定を表示および編集できます。 
   - セキュリティ リーダーは、レポート内の情報のみを表示できます。 

2. **デバイスのオンボードと構成Windowsします**。 この手順では、組織のデバイスを Defender for Business にWindowsオンボーディングできます。 デバイスのオンボードは、1 日目からデバイスを保護するのに役立ちます。 詳細については [、「オンボード デバイス to Microsoft Defender for Business」](mdb-onboard-devices.md) を参照してください。

   - Microsoft Intune (Microsoft エンドポイント マネージャー の一部) を既に使用している場合に、組織に エンドポイント マネージャー に登録されているデバイスがある場合は、登録されている Windows デバイスの一部またはすべてに対して自動オンボーディングを使用するかどうかを確認するメッセージが表示されます。 自動オンボーディングは、エンドポイント マネージャーと Defender for Business の間の接続をセットアップし、Windowsデバイスを Defender for Business にシームレスにオンボードします。

   - エンドポイント マネージャー をまだ使用していない場合、または Windows 以外のデバイスが エンドポイント マネージャー に登録されている場合は、手動で Defender for Business にデバイスをオンボードできます。 
   
3. **セキュリティ ポリシーを構成します**。 Defender for Business には、組織のデバイスに適用できる次世代保護とファイアウォール保護のための既定のセキュリティ ポリシーが含まれています。 これらの既定のポリシーは推奨設定を使用し、デバイスに強力な保護を提供するように設計されています。 

   必要に合わせ、独自のセキュリティ ポリシーを作成できます。 また、セキュリティ ポリシーを既に使用しているエンドポイント マネージャー、セキュリティ ポリシーの管理に引き続き使用できます。 

   詳細については、「セキュリティ ポリシーと [設定の表示と編集」を参照してください](mdb-configure-security-settings.md)。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>ウィザードを使用しない場合は、どうなるでしょうか。

ウィザードを使用しない場合、またはセットアップ プロセスが完了する前にウィザードが閉じている場合は、セットアップと構成プロセスを独自に完了できます。 

「 [Microsoft Defender for Business をセットアップして構成して、次](mdb-setup-configuration.md) の手順を実行する」を参照してください。

1. [セキュリティ チームがポータル](mdb-roles-permissions.md) () にアクセスして使用できるよう、役割とアクセス許可Microsoft 365 Defender割り当てます[https://security.microsoft.com](https://security.microsoft.com)。

2. [セキュリティ チームが新しいアラート](mdb-email-notifications.md) や脆弱性に関するループに入り込むので、電子メール通知を設定します。

3. [デバイスをオンボード](mdb-onboard-devices.md) して、Defender for Business によって保護されます。

4. [次世代の保護、ファイアウォール保護](mdb-configure-security-settings.md)、Web コンテンツ フィルターなど、セキュリティ ポリシーを管理します。

## <a name="next-steps"></a>次の手順

- [セキュリティ チームの電子メール通知を設定する](mdb-email-notifications.md)

- [ポータルの使用Microsoft 365 Defenderする](mdb-get-started.md)

- [[脅威の管理] &のダッシュボードを使用する](mdb-view-tvm-dashboard.md)