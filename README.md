#!/usr/bin/env python
# -*- coding: utf-8 -*-
"""
This experiment was created using PsychoPy3 Experiment Builder (v2022.1.2),
    on May 06, 2022, at 20:49
If you publish work using this script the most relevant publication is:

    Peirce J, Gray JR, Simpson S, MacAskill M, Höchenberger R, Sogo H, Kastman E, Lindeløv JK. (2019) 
        PsychoPy2: Experiments in behavior made easy Behav Res 51: 195. 
        https://doi.org/10.3758/s13428-018-01193-y

"""

from psychopy import locale_setup
from psychopy import prefs
from psychopy import sound, gui, visual, core, data, event, logging, clock, colors, layout
from psychopy.constants import (NOT_STARTED, STARTED, PLAYING, PAUSED,
                                STOPPED, FINISHED, PRESSED, RELEASED, FOREVER)

import numpy as np  # whole numpy lib is available, prepend 'np.'
from numpy import (sin, cos, tan, log, log10, pi, average,
                   sqrt, std, deg2rad, rad2deg, linspace, asarray)
from numpy.random import random, randint, normal, shuffle, choice as randchoice
import os  # handy system and path functions
import sys  # to get file system encoding

import psychopy.iohub as io
from psychopy.hardware import keyboard



# Ensure that relative paths start from the same directory as this script
_thisDir = os.path.dirname(os.path.abspath(__file__))
os.chdir(_thisDir)
# Store info about the experiment session
psychopyVersion = '2022.1.2'
expName = 'WMCTNEW'  # from the Builder filename that created this script
expInfo = {'participant': '', 'session': '001'}
dlg = gui.DlgFromDict(dictionary=expInfo, sortKeys=False, title=expName)
if dlg.OK == False:
    core.quit()  # user pressed cancel
expInfo['date'] = data.getDateStr()  # add a simple timestamp
expInfo['expName'] = expName
expInfo['psychopyVersion'] = psychopyVersion

# Data file name stem = absolute path + name; later add .psyexp, .csv, .log, etc
filename = _thisDir + os.sep + u'data/%s_%s_%s' % (expInfo['participant'], expName, expInfo['date'])

# An ExperimentHandler isn't essential but helps with data saving
thisExp = data.ExperimentHandler(name=expName, version='',
    extraInfo=expInfo, runtimeInfo=None,
    originPath='C:\\Users\\msadeghisera\\Desktop\\2- WMC task\\WMCT.py',
    savePickle=True, saveWideText=True,
    dataFileName=filename)
# save a log file for detail verbose info
logFile = logging.LogFile(filename+'.log', level=logging.EXP)
logging.console.setLevel(logging.WARNING)  # this outputs to the screen, not a file

endExpNow = False  # flag for 'escape' or other condition => quit the exp
frameTolerance = 0.001  # how close to onset before 'same' frame

# Start Code - component code to be run after the window creation

# Setup the Window
win = visual.Window(
    size=[1920, 1080], fullscr=True, screen=0, 
    winType='pyglet', allowGUI=False, allowStencil=False,
    monitor='testMonitor', color=(-1.0000, -1.0000, -1.0000), colorSpace='rgb',
    blendMode='avg', useFBO=True, 
    units='height')
# store frame rate of monitor if we can measure it
expInfo['frameRate'] = win.getActualFrameRate()
if expInfo['frameRate'] != None:
    frameDur = 1.0 / round(expInfo['frameRate'])
else:
    frameDur = 1.0 / 60.0  # could not measure, so guess
# Setup ioHub
ioConfig = {}

# Setup iohub keyboard
ioConfig['Keyboard'] = dict(use_keymap='psychopy')

ioSession = '1'
if 'session' in expInfo:
    ioSession = str(expInfo['session'])
ioServer = io.launchHubServer(window=win, **ioConfig)
eyetracker = None

# create a default keyboard (e.g. to check for escape)
defaultKeyboard = keyboard.Keyboard(backend='iohub')

# Initialize components for Routine "Welcome"
WelcomeClock = core.Clock()
welcome = visual.TextStim(win=win, name='welcome',
    text='Welcome to the experiment!',
    font='Open Sans',
    pos=(0, 0.4), height=0.06, wrapWidth=1.6, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=0.0);
instruction = visual.TextStim(win=win, name='instruction',
    text="You will see a series of equations followed by an alphabet letter. Please choose ‘True’ if the equation is correct or ‘False’ if the equation is wrong. Then, you’ll be presented an alphabet letter. In the end, after seeing ‘Type the letters in the box', please type the letters in the order they were presented to you. \n\n",
    font='Open Sans',
    pos=(0, 0), height=0.06, wrapWidth=1.6, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
example = visual.TextStim(win=win, name='example',
    text='Press [SPACE] to see two examples:',
    font='Open Sans',
    pos=(0, -0.3), height=0.06, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-2.0);
key_resp = keyboard.Keyboard()

# Initialize components for Routine "ready"
readyClock = core.Clock()
readys = visual.TextStim(win=win, name='readys',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "O1"
O1Clock = core.Clock()
Operation1 = visual.TextStim(win=win, name='Operation1',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
TF1 = visual.Slider(win=win, name='TF1',
    startValue=None, size=(0.5, 0.05), pos=(0, 0), units=None,
    labels=('True','False'), ticks=(1,2), granularity=0.0,
    style='radio', styleTweaks=(), opacity=None,
    labelColor='LightGray', markerColor=colors.Color((-1.0000, -1.0000, -1.0000), space='rgb'), lineColor='White', colorSpace='rgb',
    font='Open Sans', labelHeight=0.05,
    flip=False, ori=0.0, depth=-2, readOnly=False)

# Initialize components for Routine "L1"
L1Clock = core.Clock()
Letter1 = visual.TextStim(win=win, name='Letter1',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "O2"
O2Clock = core.Clock()
Operation2 = visual.TextStim(win=win, name='Operation2',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
TF2 = visual.Slider(win=win, name='TF2',
    startValue=None, size=(0.5, 0.05), pos=(0, 0), units=None,
    labels=('True','False'), ticks=(1,2), granularity=0.0,
    style='radio', styleTweaks=(), opacity=None,
    labelColor='LightGray', markerColor=colors.Color((-1.0000, -1.0000, -1.0000), space='rgb'), lineColor='White', colorSpace='rgb',
    font='Open Sans', labelHeight=0.05,
    flip=False, ori=0.0, depth=-2, readOnly=False)

# Initialize components for Routine "L2"
L2Clock = core.Clock()
Letter2 = visual.TextStim(win=win, name='Letter2',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "O3"
O3Clock = core.Clock()
Operation3 = visual.TextStim(win=win, name='Operation3',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
TF3 = visual.Slider(win=win, name='TF3',
    startValue=None, size=(0.5, 0.05), pos=(0, 0), units=None,
    labels=('True','False'), ticks=(1,2), granularity=0.0,
    style='radio', styleTweaks=(), opacity=None,
    labelColor='LightGray', markerColor=colors.Color((-1.0000, -1.0000, -1.0000), space='rgb'), lineColor='White', colorSpace='rgb',
    font='Open Sans', labelHeight=0.05,
    flip=False, ori=0.0, depth=-2, readOnly=False)

# Initialize components for Routine "L3"
L3Clock = core.Clock()
Letter3 = visual.TextStim(win=win, name='Letter3',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "O4"
O4Clock = core.Clock()
Operation4 = visual.TextStim(win=win, name='Operation4',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
TF4 = visual.Slider(win=win, name='TF4',
    startValue=None, size=(0.5, 0.05), pos=(0, 0), units=None,
    labels=('True','False'), ticks=(1,2), granularity=0.0,
    style='radio', styleTweaks=(), opacity=None,
    labelColor='LightGray', markerColor=colors.Color((-1.0000, -1.0000, -1.0000), space='rgb'), lineColor='White', colorSpace='rgb',
    font='Open Sans', labelHeight=0.05,
    flip=False, ori=0.0, depth=-2, readOnly=False)

# Initialize components for Routine "L4"
L4Clock = core.Clock()
Letter4 = visual.TextStim(win=win, name='Letter4',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "O5"
O5Clock = core.Clock()
Operation5 = visual.TextStim(win=win, name='Operation5',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
TF5 = visual.Slider(win=win, name='TF5',
    startValue=None, size=(0.5, 0.05), pos=(0, 0), units=None,
    labels=('True','False'), ticks=(1,2), granularity=0.0,
    style='radio', styleTweaks=(), opacity=None,
    labelColor='LightGray', markerColor=colors.Color((-1.0000, -1.0000, -1.0000), space='rgb'), lineColor='White', colorSpace='rgb',
    font='Open Sans', labelHeight=0.05,
    flip=False, ori=0.0, depth=-2, readOnly=False)

# Initialize components for Routine "L5"
L5Clock = core.Clock()
Letter5 = visual.TextStim(win=win, name='Letter5',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Initialize components for Routine "Type"
TypeClock = core.Clock()
colours = 0
Type1 = visual.TextStim(win=win, name='Type1',
    text='',
    font='Open Sans',
    pos=(0,0.25), height=0.08, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);
Typed1 = visual.TextBox2(
     win, text=None, font='Open Sans',
     pos=(0, 0.0),     letterHeight=0.07,
     size=[0.45,0.15], borderWidth=2.0,
     color=(1.0000, 1.0000, 1.0000), colorSpace='rgb',
     opacity=None,
     bold=True, italic=False,
     lineSpacing=0.01,
     padding=None, alignment='center',
     anchor='center',
     fillColor=(-1.0000, -1.0000, -1.0000), borderColor=(1.0000, 0.7882, 0.5373),
     flipHoriz=False, flipVert=False, languageStyle='LTR',
     editable=True,
     name='Typed1',
     autoLog=True,
)
key_resp_2 = keyboard.Keyboard()
text = visual.TextStim(win=win, name='text',
    text='Press [SPACE] to continue ...',
    font='Open Sans',
    pos=(0, -0.3), height=0.05, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-4.0);

# Initialize components for Routine "Practice"
PracticeClock = core.Clock()
Practice1 = visual.TextStim(win=win, name='Practice1',
    text='',
    font='Open Sans',
    pos=(0, 0), height=0.1, wrapWidth=None, ori=0.0, 
    color='white', colorSpace='rgb', opacity=None, 
    languageStyle='LTR',
    depth=-1.0);

# Create some handy timers
globalClock = core.Clock()  # to track the time since experiment started
routineTimer = core.CountdownTimer()  # to track time remaining of each (non-slip) routine 

# ------Prepare to start Routine "Welcome"-------
continueRoutine = True
# update component parameters for each repeat
key_resp.keys = []
key_resp.rt = []
_key_resp_allKeys = []
# keep track of which components have finished
WelcomeComponents = [welcome, instruction, example, key_resp]
for thisComponent in WelcomeComponents:
    thisComponent.tStart = None
    thisComponent.tStop = None
    thisComponent.tStartRefresh = None
    thisComponent.tStopRefresh = None
    if hasattr(thisComponent, 'status'):
        thisComponent.status = NOT_STARTED
# reset timers
t = 0
_timeToFirstFrame = win.getFutureFlipTime(clock="now")
WelcomeClock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
frameN = -1

# -------Run Routine "Welcome"-------
while continueRoutine:
    # get current time
    t = WelcomeClock.getTime()
    tThisFlip = win.getFutureFlipTime(clock=WelcomeClock)
    tThisFlipGlobal = win.getFutureFlipTime(clock=None)
    frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
    # update/draw components on each frame
    
    # *welcome* updates
    if welcome.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
        # keep track of start time/frame for later
        welcome.frameNStart = frameN  # exact frame index
        welcome.tStart = t  # local t and not account for scr refresh
        welcome.tStartRefresh = tThisFlipGlobal  # on global time
        win.timeOnFlip(welcome, 'tStartRefresh')  # time at next scr refresh
        welcome.setAutoDraw(True)
    
    # *instruction* updates
    if instruction.status == NOT_STARTED and tThisFlip >= 1.5-frameTolerance:
        # keep track of start time/frame for later
        instruction.frameNStart = frameN  # exact frame index
        instruction.tStart = t  # local t and not account for scr refresh
        instruction.tStartRefresh = tThisFlipGlobal  # on global time
        win.timeOnFlip(instruction, 'tStartRefresh')  # time at next scr refresh
        instruction.setAutoDraw(True)
    
    # *example* updates
    if example.status == NOT_STARTED and tThisFlip >= 1.5-frameTolerance:
        # keep track of start time/frame for later
        example.frameNStart = frameN  # exact frame index
        example.tStart = t  # local t and not account for scr refresh
        example.tStartRefresh = tThisFlipGlobal  # on global time
        win.timeOnFlip(example, 'tStartRefresh')  # time at next scr refresh
        example.setAutoDraw(True)
    
    # *key_resp* updates
    waitOnFlip = False
    if key_resp.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
        # keep track of start time/frame for later
        key_resp.frameNStart = frameN  # exact frame index
        key_resp.tStart = t  # local t and not account for scr refresh
        key_resp.tStartRefresh = tThisFlipGlobal  # on global time
        win.timeOnFlip(key_resp, 'tStartRefresh')  # time at next scr refresh
        key_resp.status = STARTED
        # keyboard checking is just starting
        waitOnFlip = True
        win.callOnFlip(key_resp.clock.reset)  # t=0 on next screen flip
    if key_resp.status == STARTED and not waitOnFlip:
        theseKeys = key_resp.getKeys(keyList=['right','space'], waitRelease=False)
        _key_resp_allKeys.extend(theseKeys)
        if len(_key_resp_allKeys):
            key_resp.keys = _key_resp_allKeys[-1].name  # just the last key pressed
            key_resp.rt = _key_resp_allKeys[-1].rt
            # a response ends the routine
            continueRoutine = False
    
    # check for quit (typically the Esc key)
    if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
        core.quit()
    
    # check if all components have finished
    if not continueRoutine:  # a component has requested a forced-end of Routine
        break
    continueRoutine = False  # will revert to True if at least one component still running
    for thisComponent in WelcomeComponents:
        if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
            continueRoutine = True
            break  # at least one component has not yet finished
    
    # refresh the screen
    if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
        win.flip()

# -------Ending Routine "Welcome"-------
for thisComponent in WelcomeComponents:
    if hasattr(thisComponent, "setAutoDraw"):
        thisComponent.setAutoDraw(False)
# check responses
if key_resp.keys in ['', [], None]:  # No response was made
    key_resp.keys = None
thisExp.addData('key_resp.keys',key_resp.keys)
if key_resp.keys != None:  # we had a response
    thisExp.addData('key_resp.rt', key_resp.rt)
thisExp.nextEntry()
# the Routine "Welcome" was not non-slip safe, so reset the non-slip timer
routineTimer.reset()

# set up handler to look after randomisation of conditions etc
trials = data.TrialHandler(nReps=1.0, method='sequential', 
    extraInfo=expInfo, originPath=-1,
    trialList=data.importConditions('WMC_DRAFT.xlsx'),
    seed=None, name='trials')
thisExp.addLoop(trials)  # add the loop to the experiment
thisTrial = trials.trialList[0]  # so we can initialise stimuli with some values
# abbreviate parameter names if possible (e.g. rgb = thisTrial.rgb)
if thisTrial != None:
    for paramName in thisTrial:
        exec('{} = thisTrial[paramName]'.format(paramName))

for thisTrial in trials:
    currentLoop = trials
    # abbreviate parameter names if possible (e.g. rgb = thisTrial.rgb)
    if thisTrial != None:
        for paramName in thisTrial:
            exec('{} = thisTrial[paramName]'.format(paramName))
    
    # ------Prepare to start Routine "ready"-------
    continueRoutine = True
    routineTimer.add(2.000000)
    # update component parameters for each repeat
    if Ready == 'blank':
        continueRoutine= False
    readys.setText(Ready)
    # keep track of which components have finished
    readyComponents = [readys]
    for thisComponent in readyComponents:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    readyClock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "ready"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = readyClock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=readyClock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *readys* updates
        if readys.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            readys.frameNStart = frameN  # exact frame index
            readys.tStart = t  # local t and not account for scr refresh
            readys.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(readys, 'tStartRefresh')  # time at next scr refresh
            readys.setAutoDraw(True)
        if readys.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > readys.tStartRefresh + 2.0-frameTolerance:
                # keep track of stop time/frame for later
                readys.tStop = t  # not accounting for scr refresh
                readys.frameNStop = frameN  # exact frame index
                win.timeOnFlip(readys, 'tStopRefresh')  # time at next scr refresh
                readys.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in readyComponents:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "ready"-------
    for thisComponent in readyComponents:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "O1"-------
    continueRoutine = True
    # update component parameters for each repeat
    if O1 == 'blank':
        continueRoutine= False
    Operation1.setText(O1)
    TF1.reset()
    # keep track of which components have finished
    O1Components = [Operation1, TF1]
    for thisComponent in O1Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    O1Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "O1"-------
    while continueRoutine:
        # get current time
        t = O1Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=O1Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Operation1* updates
        if Operation1.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Operation1.frameNStart = frameN  # exact frame index
            Operation1.tStart = t  # local t and not account for scr refresh
            Operation1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Operation1, 'tStartRefresh')  # time at next scr refresh
            Operation1.setAutoDraw(True)
        if Operation1.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Operation1.tStartRefresh + 3.5-frameTolerance:
                # keep track of stop time/frame for later
                Operation1.tStop = t  # not accounting for scr refresh
                Operation1.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Operation1, 'tStopRefresh')  # time at next scr refresh
                Operation1.setAutoDraw(False)
        
        # *TF1* updates
        if TF1.status == NOT_STARTED and tThisFlip >= 3.5-frameTolerance:
            # keep track of start time/frame for later
            TF1.frameNStart = frameN  # exact frame index
            TF1.tStart = t  # local t and not account for scr refresh
            TF1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(TF1, 'tStartRefresh')  # time at next scr refresh
            TF1.setAutoDraw(True)
        
        # Check TF1 for response to end routine
        if TF1.getRating() is not None and TF1.status == STARTED:
            continueRoutine = False
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in O1Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "O1"-------
    for thisComponent in O1Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('TF1.response', TF1.getRating())
    # the Routine "O1" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "L1"-------
    continueRoutine = True
    routineTimer.add(1.500000)
    # update component parameters for each repeat
    if L1 == 'blank':
        continueRoutine= False
    Letter1.setText(L1)
    # keep track of which components have finished
    L1Components = [Letter1]
    for thisComponent in L1Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    L1Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "L1"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = L1Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=L1Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Letter1* updates
        if Letter1.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Letter1.frameNStart = frameN  # exact frame index
            Letter1.tStart = t  # local t and not account for scr refresh
            Letter1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Letter1, 'tStartRefresh')  # time at next scr refresh
            Letter1.setAutoDraw(True)
        if Letter1.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Letter1.tStartRefresh + 1.5-frameTolerance:
                # keep track of stop time/frame for later
                Letter1.tStop = t  # not accounting for scr refresh
                Letter1.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Letter1, 'tStopRefresh')  # time at next scr refresh
                Letter1.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in L1Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "L1"-------
    for thisComponent in L1Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "O2"-------
    continueRoutine = True
    # update component parameters for each repeat
    if O2 == 'blank':
        continueRoutine= False
    Operation2.setText(O2)
    TF2.reset()
    # keep track of which components have finished
    O2Components = [Operation2, TF2]
    for thisComponent in O2Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    O2Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "O2"-------
    while continueRoutine:
        # get current time
        t = O2Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=O2Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Operation2* updates
        if Operation2.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Operation2.frameNStart = frameN  # exact frame index
            Operation2.tStart = t  # local t and not account for scr refresh
            Operation2.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Operation2, 'tStartRefresh')  # time at next scr refresh
            Operation2.setAutoDraw(True)
        if Operation2.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Operation2.tStartRefresh + 3.5-frameTolerance:
                # keep track of stop time/frame for later
                Operation2.tStop = t  # not accounting for scr refresh
                Operation2.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Operation2, 'tStopRefresh')  # time at next scr refresh
                Operation2.setAutoDraw(False)
        
        # *TF2* updates
        if TF2.status == NOT_STARTED and tThisFlip >= 3.5-frameTolerance:
            # keep track of start time/frame for later
            TF2.frameNStart = frameN  # exact frame index
            TF2.tStart = t  # local t and not account for scr refresh
            TF2.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(TF2, 'tStartRefresh')  # time at next scr refresh
            TF2.setAutoDraw(True)
        
        # Check TF2 for response to end routine
        if TF2.getRating() is not None and TF2.status == STARTED:
            continueRoutine = False
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in O2Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "O2"-------
    for thisComponent in O2Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('TF2.response', TF2.getRating())
    # the Routine "O2" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "L2"-------
    continueRoutine = True
    routineTimer.add(1.500000)
    # update component parameters for each repeat
    if L2 == 'blank':
        continueRoutine= False
    Letter2.setText(L2)
    # keep track of which components have finished
    L2Components = [Letter2]
    for thisComponent in L2Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    L2Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "L2"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = L2Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=L2Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Letter2* updates
        if Letter2.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Letter2.frameNStart = frameN  # exact frame index
            Letter2.tStart = t  # local t and not account for scr refresh
            Letter2.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Letter2, 'tStartRefresh')  # time at next scr refresh
            Letter2.setAutoDraw(True)
        if Letter2.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Letter2.tStartRefresh + 1.5-frameTolerance:
                # keep track of stop time/frame for later
                Letter2.tStop = t  # not accounting for scr refresh
                Letter2.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Letter2, 'tStopRefresh')  # time at next scr refresh
                Letter2.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in L2Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "L2"-------
    for thisComponent in L2Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "O3"-------
    continueRoutine = True
    # update component parameters for each repeat
    if O3 == 'blank':
        continueRoutine= False
    Operation3.setText(O3)
    TF3.reset()
    # keep track of which components have finished
    O3Components = [Operation3, TF3]
    for thisComponent in O3Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    O3Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "O3"-------
    while continueRoutine:
        # get current time
        t = O3Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=O3Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Operation3* updates
        if Operation3.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Operation3.frameNStart = frameN  # exact frame index
            Operation3.tStart = t  # local t and not account for scr refresh
            Operation3.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Operation3, 'tStartRefresh')  # time at next scr refresh
            Operation3.setAutoDraw(True)
        if Operation3.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Operation3.tStartRefresh + 3.5-frameTolerance:
                # keep track of stop time/frame for later
                Operation3.tStop = t  # not accounting for scr refresh
                Operation3.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Operation3, 'tStopRefresh')  # time at next scr refresh
                Operation3.setAutoDraw(False)
        
        # *TF3* updates
        if TF3.status == NOT_STARTED and tThisFlip >= 3.5-frameTolerance:
            # keep track of start time/frame for later
            TF3.frameNStart = frameN  # exact frame index
            TF3.tStart = t  # local t and not account for scr refresh
            TF3.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(TF3, 'tStartRefresh')  # time at next scr refresh
            TF3.setAutoDraw(True)
        
        # Check TF3 for response to end routine
        if TF3.getRating() is not None and TF3.status == STARTED:
            continueRoutine = False
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in O3Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "O3"-------
    for thisComponent in O3Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('TF3.response', TF3.getRating())
    # the Routine "O3" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "L3"-------
    continueRoutine = True
    routineTimer.add(1.500000)
    # update component parameters for each repeat
    if L3 == 'blank':
        continueRoutine= False
    Letter3.setText(L3)
    # keep track of which components have finished
    L3Components = [Letter3]
    for thisComponent in L3Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    L3Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "L3"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = L3Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=L3Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Letter3* updates
        if Letter3.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Letter3.frameNStart = frameN  # exact frame index
            Letter3.tStart = t  # local t and not account for scr refresh
            Letter3.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Letter3, 'tStartRefresh')  # time at next scr refresh
            Letter3.setAutoDraw(True)
        if Letter3.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Letter3.tStartRefresh + 1.5-frameTolerance:
                # keep track of stop time/frame for later
                Letter3.tStop = t  # not accounting for scr refresh
                Letter3.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Letter3, 'tStopRefresh')  # time at next scr refresh
                Letter3.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in L3Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "L3"-------
    for thisComponent in L3Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "O4"-------
    continueRoutine = True
    # update component parameters for each repeat
    if O4 == 'blank':
        continueRoutine= False
    Operation4.setText(O4)
    TF4.reset()
    # keep track of which components have finished
    O4Components = [Operation4, TF4]
    for thisComponent in O4Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    O4Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "O4"-------
    while continueRoutine:
        # get current time
        t = O4Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=O4Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Operation4* updates
        if Operation4.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Operation4.frameNStart = frameN  # exact frame index
            Operation4.tStart = t  # local t and not account for scr refresh
            Operation4.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Operation4, 'tStartRefresh')  # time at next scr refresh
            Operation4.setAutoDraw(True)
        if Operation4.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Operation4.tStartRefresh + 3.5-frameTolerance:
                # keep track of stop time/frame for later
                Operation4.tStop = t  # not accounting for scr refresh
                Operation4.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Operation4, 'tStopRefresh')  # time at next scr refresh
                Operation4.setAutoDraw(False)
        
        # *TF4* updates
        if TF4.status == NOT_STARTED and tThisFlip >= 3.5-frameTolerance:
            # keep track of start time/frame for later
            TF4.frameNStart = frameN  # exact frame index
            TF4.tStart = t  # local t and not account for scr refresh
            TF4.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(TF4, 'tStartRefresh')  # time at next scr refresh
            TF4.setAutoDraw(True)
        
        # Check TF4 for response to end routine
        if TF4.getRating() is not None and TF4.status == STARTED:
            continueRoutine = False
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in O4Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "O4"-------
    for thisComponent in O4Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('TF4.response', TF4.getRating())
    # the Routine "O4" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "L4"-------
    continueRoutine = True
    routineTimer.add(1.500000)
    # update component parameters for each repeat
    if L4 == 'blank':
        continueRoutine= False
    Letter4.setText(L4)
    # keep track of which components have finished
    L4Components = [Letter4]
    for thisComponent in L4Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    L4Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "L4"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = L4Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=L4Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Letter4* updates
        if Letter4.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Letter4.frameNStart = frameN  # exact frame index
            Letter4.tStart = t  # local t and not account for scr refresh
            Letter4.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Letter4, 'tStartRefresh')  # time at next scr refresh
            Letter4.setAutoDraw(True)
        if Letter4.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Letter4.tStartRefresh + 1.5-frameTolerance:
                # keep track of stop time/frame for later
                Letter4.tStop = t  # not accounting for scr refresh
                Letter4.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Letter4, 'tStopRefresh')  # time at next scr refresh
                Letter4.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in L4Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "L4"-------
    for thisComponent in L4Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "O5"-------
    continueRoutine = True
    # update component parameters for each repeat
    if O5 == 'blank':
        continueRoutine= False
    Operation5.setText(O5)
    TF5.reset()
    # keep track of which components have finished
    O5Components = [Operation5, TF5]
    for thisComponent in O5Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    O5Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "O5"-------
    while continueRoutine:
        # get current time
        t = O5Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=O5Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Operation5* updates
        if Operation5.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Operation5.frameNStart = frameN  # exact frame index
            Operation5.tStart = t  # local t and not account for scr refresh
            Operation5.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Operation5, 'tStartRefresh')  # time at next scr refresh
            Operation5.setAutoDraw(True)
        if Operation5.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Operation5.tStartRefresh + 3.5-frameTolerance:
                # keep track of stop time/frame for later
                Operation5.tStop = t  # not accounting for scr refresh
                Operation5.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Operation5, 'tStopRefresh')  # time at next scr refresh
                Operation5.setAutoDraw(False)
        
        # *TF5* updates
        if TF5.status == NOT_STARTED and tThisFlip >= 3.5-frameTolerance:
            # keep track of start time/frame for later
            TF5.frameNStart = frameN  # exact frame index
            TF5.tStart = t  # local t and not account for scr refresh
            TF5.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(TF5, 'tStartRefresh')  # time at next scr refresh
            TF5.setAutoDraw(True)
        
        # Check TF5 for response to end routine
        if TF5.getRating() is not None and TF5.status == STARTED:
            continueRoutine = False
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in O5Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "O5"-------
    for thisComponent in O5Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('TF5.response', TF5.getRating())
    # the Routine "O5" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "L5"-------
    continueRoutine = True
    routineTimer.add(1.500000)
    # update component parameters for each repeat
    if L5 == 'blank':
        continueRoutine= False
    Letter5.setText(L5)
    # keep track of which components have finished
    L5Components = [Letter5]
    for thisComponent in L5Components:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    L5Clock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "L5"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = L5Clock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=L5Clock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Letter5* updates
        if Letter5.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Letter5.frameNStart = frameN  # exact frame index
            Letter5.tStart = t  # local t and not account for scr refresh
            Letter5.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Letter5, 'tStartRefresh')  # time at next scr refresh
            Letter5.setAutoDraw(True)
        if Letter5.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Letter5.tStartRefresh + 1.5-frameTolerance:
                # keep track of stop time/frame for later
                Letter5.tStop = t  # not accounting for scr refresh
                Letter5.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Letter5, 'tStopRefresh')  # time at next scr refresh
                Letter5.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in L5Components:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "L5"-------
    for thisComponent in L5Components:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    
    # ------Prepare to start Routine "Type"-------
    continueRoutine = True
    # update component parameters for each repeat
    if Type == 'blank':
        continueRoutine= False
    Type1.setText(Type)
    Typed1.reset()
    Typed1.setText('')
    key_resp_2.keys = []
    key_resp_2.rt = []
    _key_resp_2_allKeys = []
    # keep track of which components have finished
    TypeComponents = [Type1, Typed1, key_resp_2, text]
    for thisComponent in TypeComponents:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    TypeClock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "Type"-------
    while continueRoutine:
        # get current time
        t = TypeClock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=TypeClock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Type1* updates
        if Type1.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Type1.frameNStart = frameN  # exact frame index
            Type1.tStart = t  # local t and not account for scr refresh
            Type1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Type1, 'tStartRefresh')  # time at next scr refresh
            Type1.setAutoDraw(True)
        
        # *Typed1* updates
        if Typed1.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Typed1.frameNStart = frameN  # exact frame index
            Typed1.tStart = t  # local t and not account for scr refresh
            Typed1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Typed1, 'tStartRefresh')  # time at next scr refresh
            Typed1.setAutoDraw(True)
        
        # *key_resp_2* updates
        waitOnFlip = False
        if key_resp_2.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            key_resp_2.frameNStart = frameN  # exact frame index
            key_resp_2.tStart = t  # local t and not account for scr refresh
            key_resp_2.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(key_resp_2, 'tStartRefresh')  # time at next scr refresh
            key_resp_2.status = STARTED
            # keyboard checking is just starting
            waitOnFlip = True
            win.callOnFlip(key_resp_2.clock.reset)  # t=0 on next screen flip
            win.callOnFlip(key_resp_2.clearEvents, eventType='keyboard')  # clear events on next screen flip
        if key_resp_2.status == STARTED and not waitOnFlip:
            theseKeys = key_resp_2.getKeys(keyList=['space'], waitRelease=False)
            _key_resp_2_allKeys.extend(theseKeys)
            if len(_key_resp_2_allKeys):
                key_resp_2.keys = _key_resp_2_allKeys[-1].name  # just the last key pressed
                key_resp_2.rt = _key_resp_2_allKeys[-1].rt
                # a response ends the routine
                continueRoutine = False
        
        # *text* updates
        if text.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            text.frameNStart = frameN  # exact frame index
            text.tStart = t  # local t and not account for scr refresh
            text.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(text, 'tStartRefresh')  # time at next scr refresh
            text.setAutoDraw(True)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in TypeComponents:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "Type"-------
    for thisComponent in TypeComponents:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    trials.addData('Typed1.text',Typed1.text)
    # check responses
    if key_resp_2.keys in ['', [], None]:  # No response was made
        key_resp_2.keys = None
    trials.addData('key_resp_2.keys',key_resp_2.keys)
    if key_resp_2.keys != None:  # we had a response
        trials.addData('key_resp_2.rt', key_resp_2.rt)
    # the Routine "Type" was not non-slip safe, so reset the non-slip timer
    routineTimer.reset()
    
    # ------Prepare to start Routine "Practice"-------
    continueRoutine = True
    routineTimer.add(3.000000)
    # update component parameters for each repeat
    if Practice == 'blank':
        continueRoutine= False
    Practice1.setText(Practice)
    # keep track of which components have finished
    PracticeComponents = [Practice1]
    for thisComponent in PracticeComponents:
        thisComponent.tStart = None
        thisComponent.tStop = None
        thisComponent.tStartRefresh = None
        thisComponent.tStopRefresh = None
        if hasattr(thisComponent, 'status'):
            thisComponent.status = NOT_STARTED
    # reset timers
    t = 0
    _timeToFirstFrame = win.getFutureFlipTime(clock="now")
    PracticeClock.reset(-_timeToFirstFrame)  # t0 is time of first possible flip
    frameN = -1
    
    # -------Run Routine "Practice"-------
    while continueRoutine and routineTimer.getTime() > 0:
        # get current time
        t = PracticeClock.getTime()
        tThisFlip = win.getFutureFlipTime(clock=PracticeClock)
        tThisFlipGlobal = win.getFutureFlipTime(clock=None)
        frameN = frameN + 1  # number of completed frames (so 0 is the first frame)
        # update/draw components on each frame
        
        # *Practice1* updates
        if Practice1.status == NOT_STARTED and tThisFlip >= 0.0-frameTolerance:
            # keep track of start time/frame for later
            Practice1.frameNStart = frameN  # exact frame index
            Practice1.tStart = t  # local t and not account for scr refresh
            Practice1.tStartRefresh = tThisFlipGlobal  # on global time
            win.timeOnFlip(Practice1, 'tStartRefresh')  # time at next scr refresh
            Practice1.setAutoDraw(True)
        if Practice1.status == STARTED:
            # is it time to stop? (based on global clock, using actual start)
            if tThisFlipGlobal > Practice1.tStartRefresh + 3.0-frameTolerance:
                # keep track of stop time/frame for later
                Practice1.tStop = t  # not accounting for scr refresh
                Practice1.frameNStop = frameN  # exact frame index
                win.timeOnFlip(Practice1, 'tStopRefresh')  # time at next scr refresh
                Practice1.setAutoDraw(False)
        
        # check for quit (typically the Esc key)
        if endExpNow or defaultKeyboard.getKeys(keyList=["escape"]):
            core.quit()
        
        # check if all components have finished
        if not continueRoutine:  # a component has requested a forced-end of Routine
            break
        continueRoutine = False  # will revert to True if at least one component still running
        for thisComponent in PracticeComponents:
            if hasattr(thisComponent, "status") and thisComponent.status != FINISHED:
                continueRoutine = True
                break  # at least one component has not yet finished
        
        # refresh the screen
        if continueRoutine:  # don't flip if this routine is over or we'll get a blank screen
            win.flip()
    
    # -------Ending Routine "Practice"-------
    for thisComponent in PracticeComponents:
        if hasattr(thisComponent, "setAutoDraw"):
            thisComponent.setAutoDraw(False)
    thisExp.nextEntry()
    
# completed 1.0 repeats of 'trials'


# Flip one final time so any remaining win.callOnFlip() 
# and win.timeOnFlip() tasks get executed before quitting
win.flip()

# these shouldn't be strictly necessary (should auto-save)
thisExp.saveAsWideText(filename+'.csv', delim='auto')
thisExp.saveAsPickle(filename)
logging.flush()
# make sure everything is closed down
if eyetracker:
    eyetracker.setConnectionState(False)
thisExp.abort()  # or data files will save again on exit
win.close()
core.quit()
