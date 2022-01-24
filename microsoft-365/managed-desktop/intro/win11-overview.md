---
title: Microsoft マネージド デスクトップと Windows 11
description: サービスで Windows 11 を使用できる方法と時間
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: b7a4366281172254a893c20dfd7519e2e8ef36d1
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62170965"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft マネージド デスクトップと Windows 11

Windows 11 の発表に続いて、Windows デバイスを最新の状態に保つ取り組みの一環として、Windows 1 Windows 10 1 の移行の計画を開始した可能性があります。 この記事では、重要な考慮事項と、Microsoft Managed Desktop が環境でのスムーズな移行をサポートする方法について説明します。 11 のWindowsについては、「Windows [11 の概要」を参照してください](/windows/whats-new/windows-11)。

Microsoft Managed Desktop デバイスにインストールされている Windows 11 を取得するための具体的な手順については、「プレビューとテスト Windows [11 with Microsoft Managed Desktop」を参照してください](../working-with-managed-desktop/test-win11-mmd.md)。

## <a name="timeline-for-windows-10-and-windows-11"></a>11 のWindows 10とWindowsタイムライン

Windows 11 は、2021 年 10 月 4 日に一般提供になりました。 コンシューマーおよびエンタープライズ展開の準備が整い、完全にサポートされているプラットフォームです。 2023 年 1 月からすべての Microsoft Managed Desktop デバイスの展開のスケジュール設定を開始しますが、2023 年 1 月 11 日より早く展開するユーザーを完全にサポートWindows予定です。 管理者に相談し、技術的な準備とビジネス上の考慮事項に基づいて、テナントごとに移行計画を開発して実装する方法をアドバイスします。

Microsoft Managed Desktop は、エンタープライズ サポートのWindows 10まで、引き続き並行してサポートを行います。 ライフ[サイクルWindows 10については、「リリース情報」](/windows/release-health/release-information)を参照してください。



## <a name="assessing-pre-release-versions-of-windows-11"></a>バージョン 11 のプレリリース バージョンWindowsする

Microsoft Managed Desktop デバイスの 95% 以上が Windows 11 の対象となるので、実稼働環境の展開前にテスト デバイスでアップグレードを試してみる必要があります。 11 のシステムWindowsの詳細については[、「11 の要件Windowsを参照してください](/windows/whats-new/windows-11-requirements)。 

Microsoft Managed Desktop デバイスの場合、デバイスを 11 テスト Windows[グループに追加できます](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#add-devices-to-the-windows-11-test-group)。 このグループは、Microsoft Windowsベースライン構成と共に、11 の一般可用性ビルドを受け取ります。 デバイス グループに追加したら、デバイスが新しい設定を受け取り、11 から 11 までWindowsします。

Microsoft Managed Desktop で管理されていないデバイスの場合は、エンドポイント マネージャー 11 を自分で展開する方法Windowsできます。 [](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/endpoint-manager-simplifies-upgrades-to-windows-11/ba-p/2771886) デバイスが 11 以降Windowsしている場合は、Microsoft Managed Desktop に登録します。デバイスは 11 以降に戻Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>11 台のデバイスのプレWindowsサポート

一般提供前にWindows 11 テストを選択したユーザーの場合、デバイスにプレビュー ビルドがインストールされている可能性があります。 この状態の Microsoft Managed Desktop デバイスには、Windows 11 の一般的な可用性ビルドは提供されませんが、発生した問題の解決には引き続きサポートされます。 さらに、Microsoft Managed Desktop は、すべての管理対象デバイスでセキュリティ上の脅威を監視し、デバイスが Windows 11 プレビュー ビルドを実行しているかどうかに関係なく、すべてのアラートに応答します。 

生産性を維持しながら、Windows 11 への移行に取り組むため、プラットフォームで発生した欠陥を報告してください。 11 の広範な展開時にユーザーの生産性をブロックする欠陥と、Windows デバイスでのユーザーの生産性をブロックする欠陥を優先Windows 10します。

## <a name="testing-application-compatibility"></a>アプリケーションの互換性のテスト

アプリケーションの互換性は、生産性の中断の可能性のために、プラットフォームの移行で最も一般的な懸念事項の 1 つです。 アプリを 11 から 11 にスムーズに移行できると確信するために、いくつかの予防的および対応的なWindowsしています。

### <a name="proactive-measures"></a>予防的な対策

**一般的なアプリ:** Microsoft では、11 のビルドに展開されている最も一般的なエンタープライズ アプリケーションとスイートWindowsします。 テスト中に検出された問題を解決するために、外部のソフトウェア発行元および内部製品チームと作業します。 プロアクティブな互換性テストの取り組みの詳細については [、「Application Compatibility blog」を参照してください](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。

**Line-of-business** アプリ: Test [Base](https://www.microsoft.com/en-us/testbase)は、アプリ発行元と IT 管理者が、Microsoft が安全な Azure 環境で Windows 11 ビルドを実行している仮想マシンで実行するためのアプリとテスト ケースの提出に使用できるリソースです。 各テスト実行の結果、テスト分析、回帰分析は、プライベート Azure ポータルで利用できます。 Microsoft Managed Desktop は、アプリの使用状況と信頼性データに基づく検証のために、業務上のアプリの優先順位を設定するのに役立ちます。 Test Base の詳細については、「Test [Base for Microsoft 365」 を参照してください](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)。

### <a name="reactive-measures"></a>反応性メジャー
テスト環境または実稼働環境でアプリの互換性の問題が発生した場合は、サービス要求を開いて無料のサポートを [受け取ります](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#report-issues)。 11 Windowsには、最新のオペレーティング システム ビルドで実行されている Office、Microsoft Edge、Teams、および line-of-business アプリケーションの機能が含まれます。 Microsoft App Assure は、必要に応じてアプリの互換性の問題に優先順位を付け、解決するためにアプリの発行元に直接関与します。

