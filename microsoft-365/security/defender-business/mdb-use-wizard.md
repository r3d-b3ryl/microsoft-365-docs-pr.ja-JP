---
title: Microsoft Defender for Businessでセットアップ ウィザードを使用する
description: Defender for Business には、ウィザードに似たセットアップと構成プロセスが含まれています。 ウィザードを使用して、時間と労力を節約します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 1f128a48e8ee2939b4bfcc270c110e0ec63d6ebe
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862590"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでセットアップ ウィザードを使用する

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

Microsoft Defender for Businessは、中小企業の時間と労力を節約するように設計されました。 たとえば、セットアップ ウィザードを使用して初期セットアップと構成を行うことができます。 セットアップ ウィザードでは、セキュリティ チームへのアクセス許可の付与、セキュリティ チームの電子メール通知の設定、会社のWindows デバイスのオンボードを行います。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="how-to-start-the-setup-wizard"></a>セットアップ ウィザードを開始する方法

セットアップ ウィザードは、会社のユーザーが Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に初めてサインインした場合に実行するように設計されています。 

会社がMicrosoft 365 Business Premiumを使用している場合は、誰かが **EndpointsDevice** >  **インベントリ** に初めてアクセスするときに Defender for Business セットアップ ウィザードが実行されます。 

セットアップ ウィザードの開始画面は、次の図のようになります。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Defender for Business を設定するためのウィザードのホーム画面のスクリーンショット。":::

## <a name="the-setup-wizard-flow"></a>セットアップ ウィザードフロー

> [!IMPORTANT]
> セットアップ ウィザードを実行するには、グローバル管理者である必要があります。 Microsoft 365またはMicrosoft Defender for Businessに会社をサインアップしたユーザーは、既定でグローバル管理者です。

セットアップ ウィザードは、Defender for Business のセットアップと構成を迅速かつ効率的に行えるように設計されています。 ウィザードでは、次の手順を実行します。

1. **ユーザーのアクセス許可を割り当てます**。 この手順では、セキュリティ チームにMicrosoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) へのアクセス権を付与します。 このポータルでは、お客様とセキュリティ チームがセキュリティ機能を管理し、アラートを表示し、検出された脅威に対して必要なアクションを実行します。 ポータルへのアクセスは、特定のアクセス許可を意味するロールを通じて付与されます。

   Defender for Business では、セキュリティ チームのメンバーに次の 3 つのロールのいずれかを割り当てることができます。<br/>
   
   - **グローバル管理者**: グローバル管理者は、Microsoft 365 テナント全体のすべての設定を表示および編集できます。 グローバル管理者は、会社のMicrosoft 365 サブスクリプションの初期セットアップと構成を行います。 
   - **セキュリティ管理者**: セキュリティ管理者は、セキュリティ設定を表示および編集し、脅威が検出されたときにアクションを実行できます。
   - **セキュリティ リーダー**: セキュリティ リーダーはレポート内の情報を表示できますが、セキュリティ設定を変更することはできません。 

   [ロールとアクセス許可の詳細については、こちらを参照してください](mdb-roles-permissions.md)。 

2. **電子メール通知を設定します**。 この手順では、セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されたとき、または新しい脆弱性が検出された場合、セキュリティ チームは、自分のデスクから離れている場合でも、そのアラートについて取り上げません。 [電子メール通知の詳細については、こちらを参照してください](mdb-email-notifications.md)。 

3. **Windowsデバイスをオンボードして構成します**。 この手順では、会社のWindows デバイスを Defender for Business にすばやくオンボードできます。 デバイスをすぐにオンボードすると、初日からデバイスを保護できます。 

   - Microsoft エンドポイント マネージャー (Microsoft Intuneを含む) を **既に使用していて**、会社にデバイスがエンドポイント マネージャーに登録されている場合は、登録済みのWindows デバイスの一部または全部に [対して自動オンボードを](#what-is-automatic-onboarding)使用するかどうかを確認するメッセージが表示されます。 自動オンボードでは、エンドポイント マネージャーと Defender for Business の間の接続が設定され、Windowsデバイスが Defender for Business にシームレスにオンボードされます。 
   - **エンドポイント マネージャーをまだ使用していない場合** は、[デバイスを Defender for Business にオンボード](mdb-onboard-devices.md)できます。 
   
   [Microsoft Defender for Businessへのデバイスのオンボードの詳細については、こちらを参照してください](mdb-onboard-devices.md)。
   
4. **セキュリティ ポリシーを構成します**。 Defender for Business には、会社のデバイスに適用できる次世代の保護とファイアウォール保護の既定のセキュリティ ポリシーが含まれています。 これらの既定のポリシーでは、推奨される設定が使用され、デバイスに強力な保護を提供するように設計されています。 独自のセキュリティ ポリシーを作成することもできます。 また、既にエンドポイント マネージャーを使用している場合は、引き続きこれを使用してセキュリティ ポリシーを管理できます。

   [セキュリティ ポリシーと設定を表示および編集します](mdb-configure-security-settings.md)。

## <a name="what-is-automatic-onboarding"></a>自動オンボードとは何ですか?

自動オンボードは、Windows デバイスを Defender for Business にオンボードする簡単な方法です。 自動オンボードは、Microsoft エンドポイント マネージャー (またはMicrosoft Intune) に既に登録されているWindows デバイスでのみ使用できます。 

セットアップ ウィザードを使用しているときに、Windows デバイスが既にエンドポイント マネージャーに登録されているかどうかをシステムが検出します。 これらのデバイスのすべてまたは一部に対して自動オンボードを使用するかどうかを確認するメッセージが表示されます。 すべてのWindows デバイスを一度にオンボードすることも、最初に特定のデバイスを選択してから、後でデバイスを追加することもできます。 

他のデバイスをオンボードするには、「[デバイスをMicrosoft Defender for Businessにオンボードする」を](mdb-onboard-devices.md)参照してください。

> [!TIP]
> - [すべてのデバイスが登録済み] オプションを選択することをお勧めします。 そうすれば、後でWindowsデバイスがエンドポイント マネージャーに登録されると、自動的に Defender for Business にオンボードされます。 
> - エンドポイント マネージャーでセキュリティ ポリシーと設定を管理している場合は、Microsoft 365 Defender ポータルに切り替えて、デバイス、ポリシー、および設定を管理することをお勧めします。 詳細については、「 [セキュリティ ポリシーとデバイスを管理する場所の選択](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)」を参照してください。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>ウィザードを使用しない場合はどうなりますか?

セットアップ ウィザードの使用は省略可能です。 ウィザードを使用しないことを選択した場合、またはセットアップ プロセスが完了する前にウィザードが閉じられる場合は、自分でセットアップと構成プロセスを完了できます。 

これらの手順については、「[Microsoft Defender for Businessのセットアップと構成](mdb-setup-configuration.md)」を参照してください。

1. セキュリティ チームが Microsoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) にアクセスして使用できるように **[、ロールとアクセス許可を割り当てます](mdb-roles-permissions.md)**。

2. 新しいアラートや脆弱性に関するループに入るように **[、セキュリティ チームの電子メール通知を設定](mdb-email-notifications.md)** します。

3. **[Defender](mdb-onboard-devices.md)** for Business によって保護されるようにデバイスをオンボードします。

4. 次世代の保護、ファイアウォール保護、Web コンテンツ のフィルター処理など、**[セキュリティ ポリシーを管理](mdb-configure-security-settings.md)** します。

## <a name="next-steps"></a>次の手順

- [より多くのデバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)
- [Microsoft Defender for Businessでセキュリティ ポリシーと設定を表示および編集する](mdb-configure-security-settings.md)