# Infonomic React/JSX Style Guide

React development at Infonomic mainly follows other 'best practice' guides and documentation - including the 'best parts' from the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) 

This style guide supplements other guides with current practices at Infonomic - not all of which are perfect, but will evolve over time. It's primarily designed to assist new developers in producing code and modules that will look familiar to everyone, making code easier to read, review, and maintain.

The rules below are in addition to relevant React/JSX rules which can be found at [Airbnb React/JSX Style Guide](https://github.com/airbnb/javascript/tree/master/react) - although note that nearly all React work at Infonomic is based on [React hooks](https://reactjs.org/docs/hooks-intro.html)

## Table of Contents

  1. [Import Rules](#import-rules)
  1. [Props](#props)
  1. [Component organization](#component-organization)

## Import Rules

  - Try to import modules in the following order - ideally with an empty line between each category
    - React core modules and hooks
    - Redux core modules and hooks
    - 3rd-party modules, libraries and hooks
    - own modules, libraries and hooks
    - 3rd-party UI components
    - own UI components
    - special tasks or actions
    - special constants or declarations

  - All React projects at Infonomic are configured to support absolute imports and so only local module files should be imported with path specifiers.

For example...

    ```jsx
    // React and 3rd-party modules, libraries and hooks
    import React, { useState } from 'react'
    import { useDispatch, useSelector } from 'react-redux'
    import { SortableContainer, SortableElement, SortableHandle } from 'react-sortable-hoc'
    import { createSelector } from 'reselect'
    import { arrayMoveImmutable } from 'array-move'
    import clsx from 'clsx'
    import { useTheme } from '@mui/system'
    import useAuthContext from 'hooks/useAuthContext'
    import { navigate, PUSH } from 'lib/router'

    // 3rd-party UI components
    import AddIcon from '@mui/icons-material/Add'
    import MoreVertIcon from '@mui/icons-material/MoreVert'
    import Box from '@mui/material/Box'
    import Button from '@mui/material/Button'
    import Fab from '@mui/material/Fab'
    import IconButton from '@mui/material/IconButton'
    import Table from '@mui/material/Table'
    import TableBody from '@mui/material/TableBody'
    import TableCell from '@mui/material/TableCell'
    import TableContainer from '@mui/material/TableContainer'
    import TableHead from '@mui/material/TableHead'
    import TableRow from '@mui/material/TableRow'

    // own UI components
    import Messages from 'modules/messages/components/Messages'
    import ContextTitle from 'ui/components/ContextTitle'
    import ItemContainer from 'ui/components/ItemContainer'
    import ItemContent from 'ui/components/ItemContent'
    import ItemFooter from 'ui/components/ItemFooter'
    import ItemHeader from 'ui/components/ItemHeader'
    import RouterButton from 'ui/components/RouterButton'
    import StyledActionMenuButton from 'ui/components/StyledActionMenuButton'

    // special declarations and tasks
    import * as L from 'locationTemplates'
    import { tasks as roleTasks } from '../actions'

    const noTextSelect = {
      '&::selection': {
        color: 'inherit',
        background: 'transparent',
      },
    }

    ```

## Props

  - Prefer destructuring props inside the component and not in the function definition of the component

    ```jsx
    // prefer
    function Foo(props) {
      const { prop1, prop2, prop3 } = props
      return <p>Foo</p>
    }
    // over
    function Foo({ prop1, prop2, prop3 }) {
      return <p>Foo</p>
    }

    ```

## Component organization

  - Prefer the following code organization for React components
    - Destructured props
    - Local state
    - Redux state
    - Hooks
    - Event handlers
    - useEffect (if present)

  For example

    ```jsx
    function Foo(props) {
      // Props
      const { prop1, prop2, prop3 } = props
      
      // Local state
      const [isSorting, setIsStorting] = useState(false)
      const [updatedOrder, setUpdatedOrder] = useState(null)
      
      // Redux state
      const roleList = useSelector(state => roleSelector(state, updatedOrder))
      
      //hooks
      const authUser = useAuthContext()
      const dispatch = useDispatch()
      
      // Event handlers - all event handlers should begin with `handle`
      const handleSubmit = event => {
        // handle submit code
      }

      //useEffect if present
      useEffect(() => {
        ...
      })

      return (
        <Box onClick={handleSubmit}>
          Click Me!
        </Box>
      );
    }
    ```

  
**[⬆ back to top](#table-of-contents)**
